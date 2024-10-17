---
{"dg-publish":true,"dg-path":"SWE-Notes/Nodriver for Scraping.md","permalink":"/swe-notes/nodriver-for-scraping/","dgHomeLink":true,"dgShowBacklinks":true,"dgShowLocalGraph":true,"dgShowInlineTitle":true,"dgShowFileTree":true,"dgEnableSearch":true,"dgShowToc":true,"dgLinkPreview":true,"dgShowTags":true,"noteIcon":1}
---


Tags: #simple #webscraping 
Sources:
- [nodriver](https://github.com/ultrafunkamsterdam/nodriver)

---

I made this small usable tool for my QA in the company: [credential repo (sorry)](https://github.com/caesariodito/automation-webifs). Quick notes, the way I made it works is mostly using the `find` syntax. I can search anything in the page, and just click it or insert something. Here is some example.

###### code example

```python
import random
import string
import logging

logging.basicConfig(level=30)

import nodriver as uc


async def main():
    driver = await uc.start()

    tab = await driver.get("https://some.url.com")

    print("finding the login button")
    login = await tab.find("Masuk atau Daftar dengan Google", best_match=True)
    print('"login" => click')
    await login.click()

    await tab

    print("finding the email input field")
    email = await tab.select("input[type=email]")

    # sometimes, email field is not shown, because phone is being asked instead
    # when this occurs, find the small text which says "use email instead"
    if not email:
        use_mail_instead = await tab.find("use email instead")
        # and click it
        await use_mail_instead.click()

        # now find the email field again
        email = await tab.select("input[type=email]")

    # send keys to email field
    print('filling in the "email" input field')
    await email.send_keys("some.email@gmail.com")

    next_btn = await tab.find(text="next", best_match=True)
    # for btn in reversed(next_btns):
    await next_btn.mouse_click()

    await tab.sleep(7)

    print("finding the password input field")
    password = await tab.select("input[type=password]")

    print('filling in the "email" input field')
    await password.send_keys("some.password")

    next_btn = await tab.find(text="next", best_match=True)
    # for btn in reversed(next_btns):
    await next_btn.mouse_click()

    await tab.sleep(3)

    # SAVE SESSION HERE
    # Saving session cookies after login
    await tab.browser.cookies.save()

    await tab.sleep(10)


if __name__ == "__main__":
    # since asyncio.run never worked (for me)
    # i use
    uc.loop().run_until_complete(main())
```

###### explanation

1. find the login button with `text`, then click it
2. find the email input form, filling it out
3. find the `next` button, then click it
4. repeat for the password
5. and then simply login

ps: you can also save and load session! so you can bypass login once after you logged in.

###### notes

The reason I love the tool is because of its simplicity syntax and usability. Why not use selenium or else? Well it can bypasses the Cloudflare challenge that prevent bots.