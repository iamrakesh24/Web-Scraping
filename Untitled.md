```python
pip install bs4 #to install beautiful soup
```

    Collecting bs4
      Downloading bs4-0.0.1.tar.gz (1.1 kB)
    Collecting beautifulsoup4
      Downloading beautifulsoup4-4.9.3-py3-none-any.whl (115 kB)
    Collecting soupsieve>1.2; python_version >= "3.0"
      Downloading soupsieve-2.2-py3-none-any.whl (33 kB)
    Using legacy 'setup.py install' for bs4, since package 'wheel' is not installed.
    Installing collected packages: soupsieve, beautifulsoup4, bs4
        Running setup.py install for bs4: started
        Running setup.py install for bs4: finished with status 'done'
    Successfully installed beautifulsoup4-4.9.3 bs4-0.0.1 soupsieve-2.2
    Note: you may need to restart the kernel to use updated packages.
    

    WARNING: You are using pip version 20.2.3; however, version 21.0.1 is available.
    You should consider upgrading via the 'c:\users\rakes\appdata\local\programs\python\python38\python.exe -m pip install --upgrade pip' command.
    


```python

```

    Requirement already satisfied: bs4 in c:\users\rakes\appdata\local\programs\python\python38\lib\site-packages (0.0.1)
    Requirement already satisfied: beautifulsoup4 in c:\users\rakes\appdata\local\programs\python\python38\lib\site-packages (from bs4) (4.9.3)
    Requirement already satisfied: soupsieve>1.2; python_version >= "3.0" in c:\users\rakes\appdata\local\programs\python\python38\lib\site-packages (from beautifulsoup4->bs4) (2.2)
    

    WARNING: You are using pip version 20.2.3; however, version 21.0.1 is available.
    You should consider upgrading via the 'c:\users\rakes\appdata\local\programs\python\python38\python.exe -m pip install --upgrade pip' command.
    


```python
from urllib.request import urlopen

```


```python
url="https://www.iplt20.com/points-table/2020" #it is the url of the page whose data needs to be scraped

```


```python
data=urlopen(url)
print(type(data)) #the datatype will be a html response
```

    <class 'http.client.HTTPResponse'>
    


```python
html=data.read() #it will provide us with the html of the page
print(html)
```

    b'<!DOCTYPE html>\n<html lang="en">\n<head>\n\n    <meta name="twitter:title" content="IPLT20.com - Indian Premier League Official Website"/>\n<meta name="keywords" content="ipl, iplt20, indian premier league, ipl cricket, ipl match, ipl live, ipl score, ipl scorecard, ipl stats, ipl schedule, ipl results, ipl points table, ipl teams, ipl videos, ipl teams, ipl news, BCCI IPL"/>\n<meta property="og:type" content="website"/>\n<meta name="description" content="Visit IPLT20.com the official IPLT20 website for minute-to-minute LIVE updates."/>\n<meta name="twitter:description" content="Visit IPLT20.com the official IPLT20 website for minute-to-minute LIVE updates."/>\n<meta property="og:title" content="IPLT20.com - Indian Premier League Official Website"/>\n<title>IPLT20.com - Indian Premier League Official Website</title>\n<meta property="og:description" content="Visit IPLT20.com the official IPLT20 website for minute-to-minute LIVE updates."/>\n\n\n    <meta charset="UTF-8">\n    <meta name="viewport" content="width=device-width, initial-scale=1">\n    <meta name="apple-itunes-app" content="app-id=509837419">\n    <meta name="theme-color" content="#263973">\n\n    <link rel="shortcut icon" href="/resources/v4.19.2/i/elements/favicon.ico" />\n\n    <script>window.RESOURCES_VERSION = \'v4.19.2\'</script>\n\n    \n<!-- Service Worker Registration -->\n<script>"serviceWorker"in navigator&&window.addEventListener("load",function(){navigator.serviceWorker.register("/sw.js?resourcesPath=v4.19.2").then(function(e){console.log("ServiceWorker successfully registered with scope: ",e.scope)},function(e){console.error("ServiceWorker registration failed: ",e)})});</script>\n\n    <!-- Service Worker Registration -->\n    <script>"serviceWorker"in navigator&&window.addEventListener("load",function(){navigator.serviceWorker.register("/sw.js?resourcesPath=v4.19.2").then(function(e){console.log("ServiceWorker successfully registered with scope: ",e.scope)},function(e){console.error("ServiceWorker registration failed: ",e)})});</script>\n\n    <link rel="preload" href="/resources/v4.19.2/fonts/SourceSansPro-Light.ttf" as="font" crossorigin>\n    <link rel="preload" href="/resources/v4.19.2/fonts/SourceSansPro-Regular.ttf" as="font" crossorigin>\n    <link rel="preload" href="/resources/v4.19.2/fonts/SourceSansPro-SemiBold.ttf" as="font" crossorigin>\n    <link rel="preload" href="/resources/v4.19.2/fonts/SourceSansPro-Bold.ttf" as="font" crossorigin>\n    <link rel="preload" href="/resources/v4.19.2/fonts/SourceSansPro-Black.ttf" as="font" crossorigin>\n\n    <link rel="stylesheet" href="/resources/v4.19.2/styles/screen.css" />\n\n</head>\n<body class="t-generic">\n    <script>\n\t(function(i,s,o,g,r,a,m){i[\'GoogleAnalyticsObject\']=r;i[r]=i[r]||function(){\n\t(i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),\n\tm=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)\n\t})(window,document,\'script\',\'//www.google-analytics.com/analytics.js\',\'ga\');\n\t\n\tga(\'create\', \'UA-11525770-1\', \'auto\');\n\tga(\'send\', \'pageview\');\n\t\n</script>\n    <div class="top-bar ">\n    <ul class="inline-list top-bar__tournament-info ">\n                <li class="inline-list__item  top-bar__tournament-info-item--bold">VIVO IPL 2021</li>\n    </ul>\n    <ul class="inline-list top-bar__logos ">\n                <li class="inline-list__item  has-link">\n                    <a class="top-bar-link bcci"\n                        href="http://www.bcci.tv/" >BCCI.tv</a>\n                </li>\n    </ul>\n        <ul class="inline-list top-bar__social">\n                    <li class="inline-list__item ">Follow IPL</li>\n                    <li class="inline-list__item  has-link">\n                        <a class="facebook"\n                            href="//www.facebook.com/ipl" target="_blank" rel="noopener">\n\t<svg class="icon ">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-facebook"></use>\n\t</svg>\n                            <span class="u-screen-reader">Facebook</span>\n                        </a>\n                    </li>\n                    <li class="inline-list__item  has-link">\n                        <a class="instagram"\n                            href="//www.instagram.com/iplt20" >\n\t<svg class="icon ">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-instagram"></use>\n\t</svg>\n                            <span class="u-screen-reader">Instagram</span>\n                        </a>\n                    </li>\n                    <li class="inline-list__item  has-link">\n                        <a class="twitter"\n                            href="//twitter.com/IPL" target="_blank" rel="noopener">\n\t<svg class="icon ">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-twitter"></use>\n\t</svg>\n                            <span class="u-screen-reader">Twitter</span>\n                        </a>\n                    </li>\n        </ul>\n    </div>\n\n<header role="banner" class="js-main-nav page-header" data-widget="main-nav" data-script="ipl_global-header">\n\t\n\n\n    <div class="js-sticky">\n        <div class="page-header__menu-wrapper">\n            <div class="page-header__logo-container">\n                <a href="/" class="page-header__logo">Indian Premier League</a>\n            </div>\n            <nav role="navigation" class="main-nav">\n                <div class="main-nav__menu-container">\n                        <div class="main-nav__mobile-strip u-show-desktop">\n                            <span class="main-nav__mobile-strip-text">VIVO IPL 2021</span>\n                        </div>\n                    <div class="main-nav__menu-container-inner js-main-menu">\n                        <ul class="main-nav__menu">\n\n\n    <li class="main-nav__menu-item  u-show-desktop">\n            <a class="main-nav__link "\n                \n                href="/">\n                Home\n            </a>\n    </li>\n\n\n    <li class="main-nav__menu-item  ">\n            <div class="main-nav__link main-nav__link--has-drop-down js-navigation-link">\n                Matches\n\t<svg class="icon main-nav__chevron-down">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-down"></use>\n\t</svg>\n            </div>\n            <div class="main-nav__drop-down nav-drop-down nav-drop-down--reveal-on-hover" tabindex="0">\n            <div class="nav-drop-down__options">\n\t<svg class="icon nav-drop-down__options-dropdown-arrow">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-arrow-block-up"></use>\n\t</svg>\n                <ul>\n                        <li class="nav-drop-down__option "\n                            data-label="Results">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/matches/results/men/2020">\n                                Results\n                            </a>\n                        </li>\n                </ul>\n            </div>\n    </li>\n\n\n    <li class="main-nav__menu-item  ">\n            <div class="main-nav__link main-nav__link--has-drop-down js-navigation-link">\n                Videos\n\t<svg class="icon main-nav__chevron-down">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-down"></use>\n\t</svg>\n            </div>\n            <div class="main-nav__drop-down nav-drop-down nav-drop-down--reveal-on-hover" tabindex="0">\n            <div class="nav-drop-down__options">\n\t<svg class="icon nav-drop-down__options-dropdown-arrow">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-arrow-block-up"></use>\n\t</svg>\n                <ul>\n                        <li class="nav-drop-down__option "\n                            data-label="Video Hub">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/video">\n                                Video Hub\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Highlights">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/video/highlights">\n                                Highlights\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Magic Moments">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/video/magic-moments">\n                                Magic Moments\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Interviews">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/video/interviews">\n                                Interviews\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Press Conferences">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/video/press-conferences">\n                                Press Conferences\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="All Videos">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/video/all">\n                                All Videos\n                            </a>\n                        </li>\n                </ul>\n            </div>\n    </li>\n\n\n    <li class="main-nav__menu-item is-active ">\n            <a class="main-nav__link is-active"\n                \n                href="/points-table">\n                Points Table\n            </a>\n    </li>\n\n\n    <li class="main-nav__menu-item  ">\n            <div class="main-nav__link main-nav__link--has-drop-down js-navigation-link">\n                Stats\n\t<svg class="icon main-nav__chevron-down">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-down"></use>\n\t</svg>\n            </div>\n            <div class="main-nav__drop-down nav-drop-down nav-drop-down--reveal-on-hover" tabindex="0">\n            <div class="nav-drop-down__options">\n\t<svg class="icon nav-drop-down__options-dropdown-arrow">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-arrow-block-up"></use>\n\t</svg>\n                <ul>\n                        <li class="nav-drop-down__option "\n                            data-label="By Season">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/stats/2020">\n                                By Season\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="All Time">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/stats/all-time">\n                                All Time\n                            </a>\n                        </li>\n                </ul>\n            </div>\n    </li>\n\n\n    <li class="main-nav__menu-item  ">\n            <a class="main-nav__link "\n                \n                href="/auction">\n                Auction\n            </a>\n    </li>\n\n\n    <li class="main-nav__menu-item  ">\n            <div class="main-nav__link main-nav__link--has-drop-down js-navigation-link">\n                Teams\n\t<svg class="icon main-nav__chevron-down">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-down"></use>\n\t</svg>\n            </div>\n            <div class="main-nav__drop-down nav-drop-down nav-drop-down--reveal-on-hover" tabindex="0">\n            <div class="nav-drop-down__options">\n\t<svg class="icon nav-drop-down__options-dropdown-arrow">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-arrow-block-up"></use>\n\t</svg>\n                <ul>\n                        <li class="nav-drop-down__option "\n                            data-label="Chennai Super Kings">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/teams/chennai-super-kings">\n                                Chennai Super Kings\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Delhi Capitals">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/teams/delhi-capitals">\n                                Delhi Capitals\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Kolkata Knight Riders">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/teams/kolkata-knight-riders">\n                                Kolkata Knight Riders\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Mumbai Indians">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/teams/mumbai-indians">\n                                Mumbai Indians\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Punjab Kings">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/teams/punjab-kings">\n                                Punjab Kings\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Rajasthan Royals">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/teams/rajasthan-royals">\n                                Rajasthan Royals\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Royal Challengers Bangalore">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/teams/royal-challengers-bangalore">\n                                Royal Challengers Bangalore\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Sunrisers Hyderabad">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/teams/sunrisers-hyderabad">\n                                Sunrisers Hyderabad\n                            </a>\n                        </li>\n                </ul>\n            </div>\n    </li>\n\n\n    <li class="main-nav__menu-item  ">\n            <div class="main-nav__link main-nav__link--has-drop-down js-navigation-link">\n                News\n\t<svg class="icon main-nav__chevron-down">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-down"></use>\n\t</svg>\n            </div>\n            <div class="main-nav__drop-down nav-drop-down nav-drop-down--reveal-on-hover" tabindex="0">\n            <div class="nav-drop-down__options">\n\t<svg class="icon nav-drop-down__options-dropdown-arrow">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-arrow-block-up"></use>\n\t</svg>\n                <ul>\n                        <li class="nav-drop-down__option "\n                            data-label="All News">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/news">\n                                All News\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Announcements">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/news/announcements">\n                                Announcements\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Match Reports">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/news/match-reports">\n                                Match Reports\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Features & Interviews">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/news/features-and-interviews">\n                                Features & Interviews\n                            </a>\n                        </li>\n                </ul>\n            </div>\n    </li>\n\n\n    <li class="main-nav__menu-item  ">\n            <div class="main-nav__link main-nav__link--has-drop-down js-navigation-link">\n                More\n\t<svg class="icon main-nav__chevron-down">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-down"></use>\n\t</svg>\n            </div>\n            <div class="main-nav__drop-down nav-drop-down nav-drop-down--reveal-on-hover" tabindex="0">\n            <div class="nav-drop-down__options">\n\t<svg class="icon nav-drop-down__options-dropdown-arrow">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-arrow-block-up"></use>\n\t</svg>\n                <ul>\n                        <li class="nav-drop-down__option "\n                            data-label="About">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/about">\n                                About\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Fantasy">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="//fantasy.iplt20.com">\n                                Fantasy\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Mobile Products">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/mobile">\n                                Mobile Products\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Photos">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/photos">\n                                Photos\n                            </a>\n                        </li>\n                        <li class="nav-drop-down__option "\n                            data-label="Venues">\n                            <a class="main-nav__link main-nav__link--in-drop-down"\n                                \n                                href="/venues">\n                                Venues\n                            </a>\n                        </li>\n                </ul>\n            </div>\n    </li>\n                        </ul>\n                    </div>\n                </div>\n                <div class="nav-footer">\n    <ul class="inline-list nav-footer__buttons nav-footer__buttons">\n                <li class="inline-list__item col-6 has-link">\n                    <a class=" btn btn--dark-blue"\n                        href="//www.bcci.tv" target="_blank" rel="noopener">BCCI.tv</a>\n                </li>\n                <li class="inline-list__item col-6 has-link">\n                    <a class=" btn btn--dark-blue"\n                        href="/" >iplt20.com</a>\n                </li>\n    </ul>\n                        <ul class="inline-list nav-footer__social social-list">\n                <li class="inline-list__item social-list__label">Follow us</li>\n                <li class="inline-list__item">\n                    <a class="facebook"\n                        href="//facebook.com/ipl" target="_blank" rel="noopener">\n\t<svg class="icon ">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-facebook"></use>\n\t</svg>\n                        <span class="u-screen-reader">Facebook</span>\n                    </a>\n                </li>\n                <li class="inline-list__item">\n                    <a class="instagram"\n                        href="//instagram.com/iplt20" target="_blank" rel="noopener">\n\t<svg class="icon ">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-instagram"></use>\n\t</svg>\n                        <span class="u-screen-reader">Instagram</span>\n                    </a>\n                </li>\n                <li class="inline-list__item">\n                    <a class="twitter"\n                        href="//twitter.com/IPL" target="_blank" rel="noopener">\n\t<svg class="icon ">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-twitter"></use>\n\t</svg>\n                        <span class="u-screen-reader">Twitter</span>\n                    </a>\n                </li>\n    </ul>\n\n                </div>\n            </nav>\n            <div class="site-search">\n                <button class="site-search__btn js-search-btn" aria-label="Search">\n                    <i class="site-search__btn-icon"></i>\n                </button>\n                <div class="pulse-poll-btn-wrapper">\n                    <button class="pulse-poll-btn js-poll-btn">\n                        <span class="pulse-poll-btn__num"></span>\n\t<svg class="icon pulse-poll-btn__icon">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-pulse"></use>\n\t</svg>\n                        <span class="pulse-poll-btn__label">Fan <br> Poll</span>\n                    </button>\n                </div>\n                <button class="burger js-burger">\n                    <div class="burger__icon">\n                        <span></span><span></span><span></span><span></span>\n                    </div>\n                    <span class="u-screen-reader">Close mobile menu</span>\n                </button>\n            </div>\n        </div>\n        <form action="/search" type="GET" class="site-search-form js-form">\n            <div class="wrapper wrapper--small site-search-form__container">\n                <input class="site-search-form__search-box js-search-input" type="text" name="term" placeholder="Search" aria-label="Search">\n                <div class="search__go">\n                    <input class="site-search-form__btn js-search-button" type="submit">\n\t<svg class="icon ">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-search"></use>\n\t</svg>\n                </div>\n            </div>\n        </form>\n    </div>\n\n\n<div class="mcContentOverlay"></div>\n<div class="pulsePoll" data-season="ipl2020" data-widget="poll" data-script="ipl_poll">\n\n    <header>\n        <div class="pulseIcon"></div>\n        <h4>Fan Poll</h4>\n        <a class="pulseButton close"><span></span></a>\n        <a class="pulseButton back"><span></span></a>\n    </header>\n    <ul class="contentSlider pulseSlide">\n        <!-- Pulse  question -->\n        <li class="slide questions contentSlide" data-view="question-list">\n            <div class="slideContent">\n                <div class="title">OPEN QUESTIONS</div>\n                <div class="empty" style="">There are currently no open questions.</div>\n                <ul class="questionList"></ul>\n                <div class="options">\n                    <a class="historyBtn voting-history-button">Voting History<span></span></a>\n                </div>\n            </div>\n        </li>\n\n        <!-- Pulse  Q&A -->\n        <li class="slide question contentSlide" data-view="question">\n            <div class="slideContent questionContainer"></div>\n            <div class="pulseHistory" style="display: none;">\n                <div class="historyResults slideContent answerContainer" style="display: none;"></div>\n                <div class="questionsList slideContent" style="display:none;">\n                    <ul class=""></ul>\n                </div>\n                <div class="empty-state slideContent" style="">\n                    <div class="title">Voting History</div>\n                    <p>A breakdown of the questions you voted on will appear here.</p>\n                </div>\n            </div>\n        </li>\n    </ul>\n\n</div><!-- END pulsePoll -->\n\n</header>\n\n    <div class="js-app-promo mobile-banner " data-script="ipl_app-promo" data-widget="app-promo">\n        <div data-widget="lazy-load-images">\n            <div class="wrapper">\n                <p class="header">IPL on the Go</p>\n                <p class="subHeader">Get all the IPL action at your fingertips</p>\n                <div class="app-buttons">\n                        <a class="app-button apple" target="_blank" rel="noopener"\n                            href="https://itunes.apple.com/in/app/iplt20/id509837419?ls=1&amp;mt=8"></a>\n                        <a class="app-button android" target="_blank" rel="noopener"\n                            href="https://play.google.com/store/apps/details?id=com.pulselive.bcci.android&amp;hl=en"></a>\n                </div>\n\n\n\n\n\n    <div class="js-lazy-load u-observed img"\n        data-picture-in-view="false"\n        data-object-fit="false"\n        data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2020/09/08/f74495c2-8feb-4efb-be7e-d78f03eac47b/Top-of-page-pushdown-promo.png?height=133&width=400"\n        data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/08/f74495c2-8feb-4efb-be7e-d78f03eac47b/Top-of-page-pushdown-promo.png?height=266&width=800"\n        data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2020/09/08/f74495c2-8feb-4efb-be7e-d78f03eac47b/Top-of-page-pushdown-promo.png?height=133&width=400"\n        data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/08/f74495c2-8feb-4efb-be7e-d78f03eac47b/Top-of-page-pushdown-promo.png?height=266&width=800"\n        data-alt="Top of page pushdown promo">\n    </div>\n\n                <button class="mobile-banner__close js-app-promo-close" aria-label="Close"></button>\n            </div>\n        </div>\n    </div>\n\n    <header class="page-heading ">\n        <div class="page-heading__background">\n\t<img class="branding-asset page-heading__background-image" src="/resources/v4.19.2/i/element-bgs/ipl_svg_background_2020-t-generic.svg" aria-hidden="true"/>\n        </div>\n        <div class="page-heading__content">\n            <h1 class="page-heading__title"> Points <span class="widget__title--bold">Table</h1>\n        </div>\n    </header>\n\n    <main id="main-content" tabindex="0">\n\t\n\t\n\n\n\n        <div class="wrapper" data-widget="dropdown-link" data-script="ipl_dropdown">\n            \n\n\n        <div class="drop-down--heading drop-down drop-down--link js-drop-down js-season-dropdown">\n            <div class="drop-down__clickzone js-dropdown-trigger" tabindex="0" role="button" aria-label="Select a Season"></div>\n            <div class="drop-down__label js-drop-down-label">Select a Season</div>\n            <div class="drop-down__current js-drop-down-current">2020 Season</div>\n            <ul class="drop-down__dropdown-list js-drop-down-options">\n                <li tabindex="0" role="button" class="drop-down__dropdown-list__option" data-option="0">\n                    <a class="drop-down__link" href="/points-table/2020">\n                        2020\n                    </a>\n                </li>\n                        <li tabindex="0" role="button" class="drop-down__dropdown-list__option" data-option="1">\n                            <a class="drop-down__link" href="/points-table/2019">\n                                2019\n                            </a>\n                        </li>\n                        <li tabindex="0" role="button" class="drop-down__dropdown-list__option" data-option="2">\n                            <a class="drop-down__link" href="/points-table/2018">\n                                2018\n                            </a>\n                        </li>\n                        <li tabindex="0" role="button" class="drop-down__dropdown-list__option" data-option="3">\n                            <a class="drop-down__link" href="/points-table/2017">\n                                2017\n                            </a>\n                        </li>\n                        <li tabindex="0" role="button" class="drop-down__dropdown-list__option" data-option="4">\n                            <a class="drop-down__link" href="/points-table/2016">\n                                2016\n                            </a>\n                        </li>\n                        <li tabindex="0" role="button" class="drop-down__dropdown-list__option" data-option="5">\n                            <a class="drop-down__link" href="/points-table/2015">\n                                2015\n                            </a>\n                        </li>\n                        <li tabindex="0" role="button" class="drop-down__dropdown-list__option" data-option="6">\n                            <a class="drop-down__link" href="/points-table/2014">\n                                2014\n                            </a>\n                        </li>\n                        <li tabindex="0" role="button" class="drop-down__dropdown-list__option" data-option="7">\n                            <a class="drop-down__link" href="/points-table/2013">\n                                2013\n                            </a>\n                        </li>\n                        <li tabindex="0" role="button" class="drop-down__dropdown-list__option" data-option="8">\n                            <a class="drop-down__link" href="/points-table/2012">\n                                2012\n                            </a>\n                        </li>\n                        <li tabindex="0" role="button" class="drop-down__dropdown-list__option" data-option="9">\n                            <a class="drop-down__link" href="/points-table/2011">\n                                2011\n                            </a>\n                        </li>\n                        <li tabindex="0" role="button" class="drop-down__dropdown-list__option" data-option="11">\n                            <a class="drop-down__link" href="/points-table/2010">\n                                2010\n                            </a>\n                        </li>\n                        <li tabindex="0" role="button" class="drop-down__dropdown-list__option" data-option="12">\n                            <a class="drop-down__link" href="/points-table/2009">\n                                2009\n                            </a>\n                        </li>\n                        <li tabindex="0" role="button" class="drop-down__dropdown-list__option" data-option="10">\n                            <a class="drop-down__link" href="/points-table/2008">\n                                2008\n                            </a>\n                        </li>\n            </ul>\n        </div>\n\n\n            <table class="standings-table standings-table--full ">\n                <tr class="standings-table__header">\n                    <th class="standings-table__freeze"></th>\n                    <th class="u-left-text standings-table__freeze">Team</th>\n                    <th class="standings-table__padded">Pld</th>\n                    <th class="standings-table__optional">Won</th>\n                    <th class="standings-table__optional">Lost</th>\n                    <th class="standings-table__optional">Tied</th>\n                    <th class="standings-table__optional">N/R</th>\n                    <th>Net RR</th>\n                    <th class="standings-table__optional">For</th>\n                    <th class="standings-table__optional">Against</th>\n                    <th>Pts</th>\n                    <th>Form</th>\n                </tr>\n                    <tr>\n        <td class="standings-table__qualified standings-table__freeze u-text-center">Q</td>\n                        <td class="standings-table__team standings-table__freeze">\n                            <i class="table__logo tLogo40x32 MI"></i>\n                            <a href="/teams/mumbai-indians">\n                            <span class="standings-table__team-name js-team">Mumbai Indians</span>\n                            <span class="standings-table__team-name standings-table__team-name--short js-team">MI</span>\n                            </a>\n                        </td>\n                        <td class="standings-table__padded">14</td>\n                        <td class="standings-table__optional">9</td>\n                        <td class="standings-table__optional">5</td>\n                        <td class="standings-table__optional">0</td>\n                        <td class="standings-table__optional">0</td>\n                        <td>+1.107</td>\n                        <td class="standings-table__optional">2,378/262.2</td>\n                        <td class="standings-table__optional">2,187/274.5</td>\n                        <td class="standings-table__highlight js-points">18</td>\n                        <td>    <ul class="standings-table__form">\n                <li class="standings-table__outcome standings-table__outcome--win standings-table__optional">W</li>\n                <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>\n                <li class="standings-table__outcome standings-table__outcome--win ">W</li>\n                <li class="standings-table__outcome standings-table__outcome--win ">W</li>\n                <li class="standings-table__outcome standings-table__outcome--loss ">L</li>\n    </ul>\n</td>\n                    </tr>\n                    <tr>\n        <td class="standings-table__qualified standings-table__freeze u-text-center">Q</td>\n                        <td class="standings-table__team standings-table__freeze">\n                            <i class="table__logo tLogo40x32 DC"></i>\n                            <a href="/teams/delhi-capitals">\n                            <span class="standings-table__team-name js-team">Delhi Capitals</span>\n                            <span class="standings-table__team-name standings-table__team-name--short js-team">DC</span>\n                            </a>\n                        </td>\n                        <td class="standings-table__padded">14</td>\n                        <td class="standings-table__optional">8</td>\n                        <td class="standings-table__optional">6</td>\n                        <td class="standings-table__optional">0</td>\n                        <td class="standings-table__optional">0</td>\n                        <td>-0.109</td>\n                        <td class="standings-table__optional">2,289/278.5</td>\n                        <td class="standings-table__optional">2,271/273</td>\n                        <td class="standings-table__highlight js-points">16</td>\n                        <td>    <ul class="standings-table__form">\n                <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>\n                <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>\n                <li class="standings-table__outcome standings-table__outcome--loss ">L</li>\n                <li class="standings-table__outcome standings-table__outcome--loss ">L</li>\n                <li class="standings-table__outcome standings-table__outcome--win ">W</li>\n    </ul>\n</td>\n                    </tr>\n                    <tr>\n        <td class="standings-table__qualified standings-table__freeze u-text-center">Q</td>\n                        <td class="standings-table__team standings-table__freeze">\n                            <i class="table__logo tLogo40x32 SRH"></i>\n                            <a href="/teams/sunrisers-hyderabad">\n                            <span class="standings-table__team-name js-team">Sunrisers Hyderabad</span>\n                            <span class="standings-table__team-name standings-table__team-name--short js-team">SRH</span>\n                            </a>\n                        </td>\n                        <td class="standings-table__padded">14</td>\n                        <td class="standings-table__optional">7</td>\n                        <td class="standings-table__optional">7</td>\n                        <td class="standings-table__optional">0</td>\n                        <td class="standings-table__optional">0</td>\n                        <td>+0.608</td>\n                        <td class="standings-table__optional">2,225/269.3</td>\n                        <td class="standings-table__optional">2,125/277.5</td>\n                        <td class="standings-table__highlight js-points">14</td>\n                        <td>    <ul class="standings-table__form">\n                <li class="standings-table__outcome standings-table__outcome--win standings-table__optional">W</li>\n                <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>\n                <li class="standings-table__outcome standings-table__outcome--win ">W</li>\n                <li class="standings-table__outcome standings-table__outcome--win ">W</li>\n                <li class="standings-table__outcome standings-table__outcome--win ">W</li>\n    </ul>\n</td>\n                    </tr>\n                    <tr>\n        <td class="standings-table__qualified standings-table__freeze u-text-center">Q</td>\n                        <td class="standings-table__team standings-table__freeze">\n                            <i class="table__logo tLogo40x32 RCB"></i>\n                            <a href="/teams/royal-challengers-bangalore">\n                            <span class="standings-table__team-name js-team">Royal Challengers Bangalore</span>\n                            <span class="standings-table__team-name standings-table__team-name--short js-team">RCB</span>\n                            </a>\n                        </td>\n                        <td class="standings-table__padded">14</td>\n                        <td class="standings-table__optional">7</td>\n                        <td class="standings-table__optional">7</td>\n                        <td class="standings-table__optional">0</td>\n                        <td class="standings-table__optional">0</td>\n                        <td>-0.172</td>\n                        <td class="standings-table__optional">2,147/272.2</td>\n                        <td class="standings-table__optional">2,183/271</td>\n                        <td class="standings-table__highlight js-points">14</td>\n                        <td>    <ul class="standings-table__form">\n                <li class="standings-table__outcome standings-table__outcome--win standings-table__optional">W</li>\n                <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>\n                <li class="standings-table__outcome standings-table__outcome--loss ">L</li>\n                <li class="standings-table__outcome standings-table__outcome--loss ">L</li>\n                <li class="standings-table__outcome standings-table__outcome--loss ">L</li>\n    </ul>\n</td>\n                    </tr>\n                    <tr>\n        <td class="standings-table__freeze u-text-center">5</td>\n                        <td class="standings-table__team standings-table__freeze">\n                            <i class="table__logo tLogo40x32 KKR"></i>\n                            <a href="/teams/kolkata-knight-riders">\n                            <span class="standings-table__team-name js-team">Kolkata Knight Riders</span>\n                            <span class="standings-table__team-name standings-table__team-name--short js-team">KKR</span>\n                            </a>\n                        </td>\n                        <td class="standings-table__padded">14</td>\n                        <td class="standings-table__optional">7</td>\n                        <td class="standings-table__optional">7</td>\n                        <td class="standings-table__optional">0</td>\n                        <td class="standings-table__optional">0</td>\n                        <td>-0.214</td>\n                        <td class="standings-table__optional">2,219/278</td>\n                        <td class="standings-table__optional">2,206/269.1</td>\n                        <td class="standings-table__highlight js-points">14</td>\n                        <td>    <ul class="standings-table__form">\n                <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>\n                <li class="standings-table__outcome standings-table__outcome--win standings-table__optional">W</li>\n                <li class="standings-table__outcome standings-table__outcome--loss ">L</li>\n                <li class="standings-table__outcome standings-table__outcome--loss ">L</li>\n                <li class="standings-table__outcome standings-table__outcome--win ">W</li>\n    </ul>\n</td>\n                    </tr>\n                    <tr>\n        <td class="standings-table__freeze u-text-center">6</td>\n                        <td class="standings-table__team standings-table__freeze">\n                            <i class="table__logo tLogo40x32 PBKS"></i>\n                            <a href="/teams/punjab-kings">\n                            <span class="standings-table__team-name js-team">Punjab Kings</span>\n                            <span class="standings-table__team-name standings-table__team-name--short js-team">PBKS</span>\n                            </a>\n                        </td>\n                        <td class="standings-table__padded">14</td>\n                        <td class="standings-table__optional">6</td>\n                        <td class="standings-table__optional">8</td>\n                        <td class="standings-table__optional">0</td>\n                        <td class="standings-table__optional">0</td>\n                        <td>-0.162</td>\n                        <td class="standings-table__optional">2,335/277.5</td>\n                        <td class="standings-table__optional">2,343/273.3</td>\n                        <td class="standings-table__highlight js-points">12</td>\n                        <td>    <ul class="standings-table__form">\n                <li class="standings-table__outcome standings-table__outcome--win standings-table__optional">W</li>\n                <li class="standings-table__outcome standings-table__outcome--win standings-table__optional">W</li>\n                <li class="standings-table__outcome standings-table__outcome--win ">W</li>\n                <li class="standings-table__outcome standings-table__outcome--loss ">L</li>\n                <li class="standings-table__outcome standings-table__outcome--loss ">L</li>\n    </ul>\n</td>\n                    </tr>\n                    <tr>\n        <td class="standings-table__freeze u-text-center">7</td>\n                        <td class="standings-table__team standings-table__freeze">\n                            <i class="table__logo tLogo40x32 CSK"></i>\n                            <a href="/teams/chennai-super-kings">\n                            <span class="standings-table__team-name js-team">Chennai Super Kings</span>\n                            <span class="standings-table__team-name standings-table__team-name--short js-team">CSK</span>\n                            </a>\n                        </td>\n                        <td class="standings-table__padded">14</td>\n                        <td class="standings-table__optional">6</td>\n                        <td class="standings-table__optional">8</td>\n                        <td class="standings-table__optional">0</td>\n                        <td class="standings-table__optional">0</td>\n                        <td>-0.455</td>\n                        <td class="standings-table__optional">2,191/274.3</td>\n                        <td class="standings-table__optional">2,275/269.4</td>\n                        <td class="standings-table__highlight js-points">12</td>\n                        <td>    <ul class="standings-table__form">\n                <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>\n                <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>\n                <li class="standings-table__outcome standings-table__outcome--win ">W</li>\n                <li class="standings-table__outcome standings-table__outcome--win ">W</li>\n                <li class="standings-table__outcome standings-table__outcome--win ">W</li>\n    </ul>\n</td>\n                    </tr>\n                    <tr>\n        <td class="standings-table__freeze u-text-center">8</td>\n                        <td class="standings-table__team standings-table__freeze">\n                            <i class="table__logo tLogo40x32 RR"></i>\n                            <a href="/teams/rajasthan-royals">\n                            <span class="standings-table__team-name js-team">Rajasthan Royals</span>\n                            <span class="standings-table__team-name standings-table__team-name--short js-team">RR</span>\n                            </a>\n                        </td>\n                        <td class="standings-table__padded">14</td>\n                        <td class="standings-table__optional">6</td>\n                        <td class="standings-table__optional">8</td>\n                        <td class="standings-table__optional">0</td>\n                        <td class="standings-table__optional">0</td>\n                        <td>-0.569</td>\n                        <td class="standings-table__optional">2,288/272.4</td>\n                        <td class="standings-table__optional">2,482/277</td>\n                        <td class="standings-table__highlight js-points">12</td>\n                        <td>    <ul class="standings-table__form">\n                <li class="standings-table__outcome standings-table__outcome--win standings-table__optional">W</li>\n                <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>\n                <li class="standings-table__outcome standings-table__outcome--win ">W</li>\n                <li class="standings-table__outcome standings-table__outcome--win ">W</li>\n                <li class="standings-table__outcome standings-table__outcome--loss ">L</li>\n    </ul>\n</td>\n                    </tr>\n            </table>\n        </div>\n\n\n</main>\n\n\n<div class="modal" id="videoPlayer" data-widget="modal">\n    <div class="modal__inner-wrapper">\n        <a href="#" class="modal__close js-modal-close">\n            <svg class="icon"><use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-close"></use></svg>\n        </a>\n        <div class="fixed-cols fixed-cols--modal fixed-cols--t-dark">\n            <div class="flex-grid">\n                <div class="col-9 col-8-wide col-12-desk col-12-m fixed-cols__primary js-main-col">\n                    <div class="fixed-cols__primary-top js-single-video">\n                        <section class="video-player video-player--modal wrapper" data-widget="video-page-player" data-player-name="playlistPlayer">\n                            <div class="inline-player"\n                                data-script="ipl_video"\n                                data-widget="video-player">\n\n                                <video id="playlistPlayer"\n                                    data-video-id=""\n                                    data-account="3588749423001"\n                                    data-player="H1Xzd8U6g"\n                                    data-embed="default"\n                                    class="inline-player__content video-js"\n                                    controls\n                                    autoplay=true\n                                    data-tracker-action="VIEW"\n                                    data-tracker-type="VIDEO"\n                                    data-tracker-id=""></video>\n                            </div>\n                            <div class="video-player__details col-12">\n                                <h1 class="video-player__title js-player-title"></h1>\n                                <p class="video-player__description js-player-description"></p>\n                                <ul class="inline-list">\n                                    <li>\n\t<svg class="icon video-player__watch-icn">\n\t\t<use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-eye"></use>\n\t</svg>\n                                        <strong class="js-main-player-views"></strong>\n                                    </li>\n                                    <li class="video-player__date js-player-date"></li>\n                                </ul>\n                            </div>\n                            <div class="video-player__share col-10 col-12-tab js-video-share">\n                            </div>\n                        </section>\n\n                    </div>\n                    <div class="fixed-cols__primary-bottom js-additional-content u-hide-desktop">\n                        <section class="widget"\n                            data-widget="content-list-loader"\n                            data-title="Magic Moments"\n                            data-tags="ipl-magic,indian-premier-league"\n                            data-link-to="/video/magic-moments"\n                            data-content-type="video"></section>\n                        <section class="widget"\n                            data-widget="content-list-loader"\n                            data-title="Latest Videos"\n                            data-tags="indian-premier-league"\n                            data-link-to="/video/all"\n                            data-content-type="video"></section>\n                    </div>\n                </div>\n                <div class="col-3 col-4-wide col-12-desk fixed-cols__secondary js-video-sidebar js-sidebar-desktop">\n\n                </div>\n            </div>\n        </div>\n    </div>\n</div>\n\n\n<footer class="page-footer" role="contentinfo">\n    \n<div class="promo-list">\n    <div class="wrapper">\n        <ul class="promo-list__items">\n\n\n                    <li class="promo-list__item">\n                            <span class="promo-list__title">Title Sponsor</span>\n    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">\n            <a href="https://www.vivo.com/in/" target="_self" class="promo-list__sponsor">\n        <div class="js-lazy-load u-observable"\n            data-picture-in-view="false"\n            data-object-fit="false"\n            data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2021/02/09/a67d89ee-5a3b-44ff-b1c3-3f8c50f4cd20/Vivo-Sample-3.png?height=60&width=168"\n            data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2021/02/09/a67d89ee-5a3b-44ff-b1c3-3f8c50f4cd20/Vivo-Sample-3.png?height=120&width=336"\n            data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2021/02/09/a67d89ee-5a3b-44ff-b1c3-3f8c50f4cd20/Vivo-Sample-3.png?height=60&width=168"\n            data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2021/02/09/a67d89ee-5a3b-44ff-b1c3-3f8c50f4cd20/Vivo-Sample-3.png?height=120&width=336"\n            data-alt="VIVO - Title Sponsor">\n        </div>\n            </a>\n    </div>\n                    </li>\n        </ul>\n    </div>\n</div>\n\n\n<div class="promo-list">\n    <div class="wrapper">\n        <ul class="promo-list__items">\n\n\n                    <li class="promo-list__item">\n                            <span class="promo-list__title">Official Broadcaster</span>\n    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">\n            <a href="https://www.hotstar.com/" target="_self" class="promo-list__sponsor">\n        <div class="js-lazy-load u-observable"\n            data-picture-in-view="false"\n            data-object-fit="false"\n            data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/d09cbee2-420c-4950-a25c-bedb0cb491bf/star-sports.png?height=80&width=100"\n            data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/d09cbee2-420c-4950-a25c-bedb0cb491bf/star-sports.png?height=160&width=200"\n            data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/d09cbee2-420c-4950-a25c-bedb0cb491bf/star-sports.png?height=80&width=100"\n            data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/d09cbee2-420c-4950-a25c-bedb0cb491bf/star-sports.png?height=160&width=200"\n            data-alt="Star Sports - Partner">\n        </div>\n            </a>\n    </div>\n                    </li>\n\n\n                    <li class="promo-list__item">\n                            <span class="promo-list__title">Official Digital Streaming Partner</span>\n    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">\n            <a href="https://www.hotstar.com/" target="_blank" rel="nofollow" class="promo-list__sponsor">\n        <div class="js-lazy-load u-observable"\n            data-picture-in-view="false"\n            data-object-fit="false"\n            data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/15265897-583c-4216-b643-9705df72b6fe/sponsor-hotstar.png?height=80&width=100"\n            data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/15265897-583c-4216-b643-9705df72b6fe/sponsor-hotstar.png?height=160&width=200"\n            data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/15265897-583c-4216-b643-9705df72b6fe/sponsor-hotstar.png?height=80&width=100"\n            data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/15265897-583c-4216-b643-9705df72b6fe/sponsor-hotstar.png?height=160&width=200"\n            data-alt="Disney+ Hotstar - Sponsor">\n        </div>\n            </a>\n    </div>\n                    </li>\n\n\n                    <li class="promo-list__item promo-list__item--multiple">\n                        <span class="promo-list__title">Official Partners</span>\n                        <ul class="inline-list promo-list__sub-list">\n                            <li>\n    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">\n            <a href="https://cars.tatamotors.com/suv/safari" target="_self" class="promo-list__sponsor">\n        <div class="js-lazy-load u-observable"\n            data-picture-in-view="false"\n            data-object-fit="false"\n            data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2021/02/12/1ef4ebc7-e65b-4ede-a11d-05bb46928578/safari-logo-png.png?height=36&width=136"\n            data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2021/02/12/1ef4ebc7-e65b-4ede-a11d-05bb46928578/safari-logo-png.png?height=72&width=272"\n            data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2021/02/12/1ef4ebc7-e65b-4ede-a11d-05bb46928578/safari-logo-png.png?height=36&width=136"\n            data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2021/02/12/1ef4ebc7-e65b-4ede-a11d-05bb46928578/safari-logo-png.png?height=72&width=272"\n            data-alt="Safari - Official Partner">\n        </div>\n            </a>\n    </div>\n                            </li>\n\n\n                    <li class="">\n    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">\n            <a href="https://www.dream11.com/" target="_self" class="promo-list__sponsor">\n        <div class="js-lazy-load u-observable"\n            data-picture-in-view="false"\n            data-object-fit="false"\n            data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2021/02/12/dedd475c-fc82-47d6-a992-1f5e5c2d0b1e/dream-11-final-logo.png?height=34&width=128.5"\n            data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2021/02/12/dedd475c-fc82-47d6-a992-1f5e5c2d0b1e/dream-11-final-logo.png?height=68&width=257"\n            data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2021/02/12/dedd475c-fc82-47d6-a992-1f5e5c2d0b1e/dream-11-final-logo.png?height=34&width=128.5"\n            data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2021/02/12/dedd475c-fc82-47d6-a992-1f5e5c2d0b1e/dream-11-final-logo.png?height=68&width=257"\n            data-alt="Dream11 - Official Partner">\n        </div>\n            </a>\n    </div>\n                    </li>\n\n\n                    <li class="">\n    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">\n            <a href="https://unacademy.com/" target="_blank" rel="nofollow" class="promo-list__sponsor">\n        <div class="js-lazy-load u-observable"\n            data-picture-in-view="false"\n            data-object-fit="false"\n            data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/a11c9b5b-41b1-4617-ab37-a89d97e1fc2e/sponsor-unacademy.png?height=19&width=120"\n            data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/a11c9b5b-41b1-4617-ab37-a89d97e1fc2e/sponsor-unacademy.png?height=38&width=240"\n            data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/a11c9b5b-41b1-4617-ab37-a89d97e1fc2e/sponsor-unacademy.png?height=19&width=120"\n            data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/a11c9b5b-41b1-4617-ab37-a89d97e1fc2e/sponsor-unacademy.png?height=38&width=240"\n            data-alt="Official Partner - Unacademy">\n        </div>\n            </a>\n    </div>\n                    </li>\n\n\n                            <li>\n    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">\n            <a href="https://www.cred.club/" target="_blank" rel="nofollow" class="promo-list__sponsor">\n        <div class="js-lazy-load u-observable"\n            data-picture-in-view="false"\n            data-object-fit="false"\n            data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2020/09/14/171bb205-b523-42a0-9f3c-eff541cdf35f/cred-new-2.png?height=38&width=85.5"\n            data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/14/171bb205-b523-42a0-9f3c-eff541cdf35f/cred-new-2.png?height=76&width=171"\n            data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2020/09/14/171bb205-b523-42a0-9f3c-eff541cdf35f/cred-new-2.png?height=38&width=85.5"\n            data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/14/171bb205-b523-42a0-9f3c-eff541cdf35f/cred-new-2.png?height=76&width=171"\n            data-alt="Cred - Official Partners">\n        </div>\n            </a>\n    </div>\n                            </li>\n                        </ul>\n                    </li>\n\n\n                    <li class="promo-list__item">\n                            <span class="promo-list__title">Umpire Partner</span>\n    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">\n            <a href="https://paytm.com/" target="_self" class="promo-list__sponsor">\n        <div class="js-lazy-load u-observable"\n            data-picture-in-view="false"\n            data-object-fit="false"\n            data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/b1771f68-719a-4b2d-9db4-944f3b47b66e/sponsor-paytm.png?height=25&width=81"\n            data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/b1771f68-719a-4b2d-9db4-944f3b47b66e/sponsor-paytm.png?height=50&width=162"\n            data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/b1771f68-719a-4b2d-9db4-944f3b47b66e/sponsor-paytm.png?height=25&width=81"\n            data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/b1771f68-719a-4b2d-9db4-944f3b47b66e/sponsor-paytm.png?height=50&width=162"\n            data-alt="Paytm - Partner">\n        </div>\n            </a>\n    </div>\n                    </li>\n\n\n                    <li class="promo-list__item">\n                            <span class="promo-list__title">Official Strategic Timeout Partner</span>\n    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">\n            <a href="https://www.ceat.com/" target="_blank" rel="nofollow" class="promo-list__sponsor">\n        <div class="js-lazy-load u-observable"\n            data-picture-in-view="false"\n            data-object-fit="false"\n            data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/57a112b9-cc79-4375-8033-b5234db3ae51/sponsor-ceat.png?height=22&width=74"\n            data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/57a112b9-cc79-4375-8033-b5234db3ae51/sponsor-ceat.png?height=44&width=148"\n            data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/57a112b9-cc79-4375-8033-b5234db3ae51/sponsor-ceat.png?height=22&width=74"\n            data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/57a112b9-cc79-4375-8033-b5234db3ae51/sponsor-ceat.png?height=44&width=148"\n            data-alt="CEAT - Sponsor">\n        </div>\n            </a>\n    </div>\n                    </li>\n        </ul>\n    </div>\n</div>\n\n\n<div class="page-footer__nav-section">\n    <div class="page-footer__background">\n\t<img class="branding-asset page-footer__background-image" src="/resources/v4.19.2/i/element-bgs/ipl_svg_background_2020-t-generic.svg" aria-hidden="true"/>\n    <div class="social-follow social-follow--footer">\n        <h5 class="social-follow__title u-hide-phablet">FOLLOW #IPL</h5>\n        <ul class="social-follow__list">\n            <li class="social-follow__item">\n                <a href="https://www.facebook.com/IPL/" target="_blank" rel="nofollow" class="social-follow__link social-follow__link--facebook js-facebook-link">\n                    <svg class="icon"><use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-facebook"></use></svg>\n                    <span class="u-screen-reader">Follow IPL on Facebook</span>\n                </a>\n            </li>\n            <li class="social-follow__item">\n                <a href="https://www.instagram.com/iplt20/?hl=en" target="_blank" rel="nofollow" class="social-follow__link social-follow__link--instagram js-instagram-link">\n                    <svg class="icon"><use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-instagram"></use></svg>\n                    <span class="u-screen-reader">Follow IPL on Instagram</span>\n                </a>\n            </li>\n            <li class="social-follow__item">\n                <a href="https://twitter.com/IPL" target="_blank" rel="nofollow" class="social-follow__link social-follow__link--twitter js-twitter-link">\n                    <svg class="icon"><use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-twitter"></use></svg>\n                    <span class="u-screen-reader">Follow IPL on Twitter</span>\n                </a>\n            </li>\n        </ul>\n    </div>\n        <div class="col-12">\n            <nav class="page-footer__menu">\n                <ul class="large-block-grid-5 small-block-grid-1">\n\t                <li>\n                        <h5 class="footer-list__title">Quicklinks</h5>\n\t\t\t\t\t\t<ul class="footer-list large-block-grid-1 medium-block-grid-3 small-block-grid-2">\n                \t<li><a href="/news">News</a></li>\n                \t<li><a href="/video">Videos</a></li>\n                \t<li><a href="/venues">Venues</a></li>\n                \t<li><a href="/stats">Stats</a></li>\n                \t<li><a href="/archive">Archive</a></li>\n\t\t\t\t\t\t</ul>\n\t\t\t\t\t</li>\n\t                <li>\n                        <h5 class="footer-list__title">Teams</h5>\n\t\t\t\t\t\t<ul class="footer-list large-block-grid-1 medium-block-grid-3 small-block-grid-2">\n                \t<li><a href="/teams/chennai-super-kings">Chennai Super Kings</a></li>\n                \t<li><a href="/teams/delhi-capitals">Delhi Capitals</a></li>\n                \t<li><a href="/teams/kings-xi-punjab">Kings XI Punjab</a></li>\n                \t<li><a href="/teams/kolkata-knight-riders">Kolkata Knight Riders</a></li>\n                \t<li><a href="/teams/mumbai-indians">Mumbai Indians</a></li>\n                \t<li><a href="/teams/rajasthan-royals">Rajasthan Royals</a></li>\n                \t<li><a href="/teams/royal-challengers-bangalore">Royal Challengers Bangalore</a></li>\n                \t<li><a href="/teams/sunrisers-hyderabad">Sunrisers Hyderabad</a></li>\n\t\t\t\t\t\t</ul>\n\t\t\t\t\t</li>\n\t                <li>\n                        <h5 class="footer-list__title">About</h5>\n\t\t\t\t\t\t<ul class="footer-list large-block-grid-1 medium-block-grid-3 small-block-grid-2">\n                \t<li><a href="/about/about-us">About Us</a></li>\n                \t<li><a href="/about/anti-corruption-policy">Anti Corruption Policy</a></li>\n                \t<li><a href="/about/anti-doping-policy">Anti Doping Policy</a></li>\n                \t<li><a href="https://iplplatform-static-files.s3.amazonaws.com/IPL/document/2020/01/23/6beaa665-8850-4ad0-8d64-baa0967a818f/TUE-Form.pdf">TUE Application Form</a></li>\n                \t<li><a href="/about/anti-racism-policy">Anti-Discrimination Policy</a></li>\n                \t<li><a href="/about/clothing-and-equipment-regulations">Clothing and Equipment Regulations</a></li>\n                \t<li><a href="/about/code-of-conduct-for-players-and-team-officials">Code of Conduct for Players and Team Officials</a></li>\n\t\t\t\t\t\t</ul>\n\t\t\t\t\t</li>\n\t                <li>\n                        <h5 class="footer-list__title">Title</h5>\n\t\t\t\t\t\t<ul class="footer-list large-block-grid-1 medium-block-grid-3 small-block-grid-2">\n                \t<li><a href="/about/code-of-conduct-for-umpires">IPL Code of Conduct for Match officials</a></li>\n                \t<li><a href="https://resources.platform.iplt20.com/IPL/document/2020/09/13/e81ad3af-a65c-4b95-a0d6-cd7840acf20f/IPL-2020-Brand-and-Content-Protection-Guidelines.pdf">Brand and Protection Guidelines</a></li>\n                \t<li><a href="/about/governing-council">Governing Council</a></li>\n                \t<li><a href="/about/match-playing-conditions">Match Playing Conditions</a></li>\n                \t<li><a href="/about/pmoa-minimum-standard">PMOA Minimum Standard</a></li>\n                \t<li><a href="/about/suspect-action-policy">Suspect Action Policy</a></li>\n\t\t\t\t\t\t</ul>\n\t\t\t\t\t</li>\n\t                <li>\n                        <h5 class="footer-list__title">Contact</h5>\n\t\t\t\t\t\t<ul class="footer-list large-block-grid-1 medium-block-grid-3 small-block-grid-2">\n                \t<li><a href="/about/contact-us">Contact Us</a></li>\n                \t<li><a href="/about/contact-us">Sponsorship</a></li>\n\t\t\t\t\t\t</ul>\n\t\t\t\t\t</li>\n                </ul>\n            </nav>\n        </div>\n    </div>\n</div>\n\n<div class="page-footer__bottom">\n    <div class="page-footer__bottom-content">\n        \n<span class="ipl-copy">&copy; Copyright IPL, BCCI 2021. All Rights Reserved.</span>\n\n<ul class="foot-menu inline-list">\n\t\t\t<li><a href="/about/privacy-policy">Privacy Policy</a></li>\n</ul>\n\n    </div>\n</div>\n\n</footer>\n\n<section class="match-scroller-container">\n    \n\n<div class="match-scroller__fixed-container">\n    <section class="match-scroller"\n    data-widget="match-scroller"\n    data-script="ipl_match-scroller">\n        <nav class="match-scroller__nav js-match-scroller-nav">\n            <button class="match-scroller__btn match-scroller__btn--prev js-match-scroller-prev" aria-label="Previous">\n                <svg class="icon"><use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-left"></use></svg>\n            </button>\n            <button class="match-scroller__btn match-scroller__btn--next js-match-scroller-next" aria-label="Next">\n                <svg class="icon"><use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-right"></use></svg>\n            </button>\n        </nav>\n        <ul class="match-scroller__list js-match-scroller-list scroller-toggle slider-fixtures">\n\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Sep</span>\n                            <span class="match-scroller__day">19</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/01"\n        class="match-item  js-match-item "\n        data-match-id="22236"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1600524000000">\n            <p class="match-item__summary">Chennai Super Kings won by 5 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-MI">\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n                <div class="match-item__team-logo tLogo70x MI"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    162\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        9\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    166\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-CSK">\n                <div class="match-item__team-logo tLogo70x CSK"></div>\n                <p class="match-item__team-name" title="Chennai Super Kings">\n                    CSK\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Sep</span>\n                            <span class="match-scroller__day">20</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/02"\n        class="match-item  js-match-item "\n        data-match-id="22237"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1600610400000">\n            <p class="match-item__summary">Match tied (Delhi Capitals won the Super Over)</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-DC">\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n                <div class="match-item__team-logo tLogo70x DC"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    157\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        8\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    157\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        8\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-PBKS">\n                <div class="match-item__team-logo tLogo70x PBKS"></div>\n                <p class="match-item__team-name" title="Punjab Kings">\n                    PBKS\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Sep</span>\n                            <span class="match-scroller__day">21</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/03"\n        class="match-item  js-match-item "\n        data-match-id="22238"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1600696800000">\n            <p class="match-item__summary">Royal Challengers Bangalore won by 10 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-SRH">\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    153\n                </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    163\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RCB">\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Sep</span>\n                            <span class="match-scroller__day">22</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/04"\n        class="match-item  js-match-item "\n        data-match-id="22239"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1600783200000">\n            <p class="match-item__summary">Rajasthan Royals won by 16 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-RR">\n                <p class="match-item__team-name" title="Rajasthan Royals">\n                    RR\n                </p>\n                <div class="match-item__team-logo tLogo70x RR"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    216\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        7\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    200\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-CSK">\n                <div class="match-item__team-logo tLogo70x CSK"></div>\n                <p class="match-item__team-name" title="Chennai Super Kings">\n                    CSK\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Sep</span>\n                            <span class="match-scroller__day">23</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/05"\n        class="match-item  js-match-item "\n        data-match-id="22240"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1600869600000">\n            <p class="match-item__summary">Mumbai Indians won by 49 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-KKR">\n                <p class="match-item__team-name" title="Kolkata Knight Riders">\n                    KKR\n                </p>\n                <div class="match-item__team-logo tLogo70x KKR"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    146\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        9\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    195\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-MI">\n                <div class="match-item__team-logo tLogo70x MI"></div>\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Sep</span>\n                            <span class="match-scroller__day">24</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/06"\n        class="match-item  js-match-item "\n        data-match-id="22241"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1600956000000">\n            <p class="match-item__summary">Punjab Kings won by 97 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-PBKS">\n                <p class="match-item__team-name" title="Punjab Kings">\n                    PBKS\n                </p>\n                <div class="match-item__team-logo tLogo70x PBKS"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    206\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        3\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    109\n                </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RCB">\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Sep</span>\n                            <span class="match-scroller__day">25</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/07"\n        class="match-item  js-match-item "\n        data-match-id="22242"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1601042400000">\n            <p class="match-item__summary">Delhi Capitals won by 44 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-CSK">\n                <p class="match-item__team-name" title="Chennai Super Kings">\n                    CSK\n                </p>\n                <div class="match-item__team-logo tLogo70x CSK"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    131\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        7\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    175\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        3\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-DC">\n                <div class="match-item__team-logo tLogo70x DC"></div>\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Sep</span>\n                            <span class="match-scroller__day">26</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/08"\n        class="match-item  js-match-item "\n        data-match-id="22243"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1601128800000">\n            <p class="match-item__summary">Kolkata Knight Riders won by 7 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-KKR">\n                <p class="match-item__team-name" title="Kolkata Knight Riders">\n                    KKR\n                </p>\n                <div class="match-item__team-logo tLogo70x KKR"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    145\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        3\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    142\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-SRH">\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Sep</span>\n                            <span class="match-scroller__day">27</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/09"\n        class="match-item  js-match-item "\n        data-match-id="22244"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1601215200000">\n            <p class="match-item__summary">Rajasthan Royals won by 4 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-RR">\n                <p class="match-item__team-name" title="Rajasthan Royals">\n                    RR\n                </p>\n                <div class="match-item__team-logo tLogo70x RR"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    226\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    223\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        2\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-PBKS">\n                <div class="match-item__team-logo tLogo70x PBKS"></div>\n                <p class="match-item__team-name" title="Punjab Kings">\n                    PBKS\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Sep</span>\n                            <span class="match-scroller__day">28</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/10"\n        class="match-item  js-match-item "\n        data-match-id="22245"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1601301600000">\n            <p class="match-item__summary">Match tied (Royal Challengers Bangalore won the Super Over)</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-RCB">\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    201\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        3\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    201\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-MI">\n                <div class="match-item__team-logo tLogo70x MI"></div>\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Sep</span>\n                            <span class="match-scroller__day">29</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/11"\n        class="match-item  js-match-item "\n        data-match-id="22246"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1601388000000">\n            <p class="match-item__summary">Sunrisers Hyderabad won by 15 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-DC">\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n                <div class="match-item__team-logo tLogo70x DC"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    147\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        7\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    162\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-SRH">\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Sep</span>\n                            <span class="match-scroller__day">30</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/12"\n        class="match-item  js-match-item "\n        data-match-id="22247"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1601474400000">\n            <p class="match-item__summary">Kolkata Knight Riders won by 37 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-RR">\n                <p class="match-item__team-name" title="Rajasthan Royals">\n                    RR\n                </p>\n                <div class="match-item__team-logo tLogo70x RR"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    137\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        9\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    174\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-KKR">\n                <div class="match-item__team-logo tLogo70x KKR"></div>\n                <p class="match-item__team-name" title="Kolkata Knight Riders">\n                    KKR\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">1</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/13"\n        class="match-item  js-match-item "\n        data-match-id="22248"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1601560800000">\n            <p class="match-item__summary">Mumbai Indians won by 48 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-PBKS">\n                <p class="match-item__team-name" title="Punjab Kings">\n                    PBKS\n                </p>\n                <div class="match-item__team-logo tLogo70x PBKS"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    143\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        8\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    191\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-MI">\n                <div class="match-item__team-logo tLogo70x MI"></div>\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">2</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/14"\n        class="match-item  js-match-item "\n        data-match-id="22249"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1601647200000">\n            <p class="match-item__summary">Sunrisers Hyderabad won by 7 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-CSK">\n                <p class="match-item__team-name" title="Chennai Super Kings">\n                    CSK\n                </p>\n                <div class="match-item__team-logo tLogo70x CSK"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    157\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    164\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-SRH">\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">3</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/15"\n        class="match-item  js-match-item "\n        data-match-id="22250"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1601719200000">\n            <p class="match-item__summary">Royal Challengers Bangalore won by 8 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-RCB">\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    158\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        2\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    154\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RR">\n                <div class="match-item__team-logo tLogo70x RR"></div>\n                <p class="match-item__team-name" title="Rajasthan Royals">\n                    RR\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/16"\n        class="match-item  js-match-item "\n        data-match-id="22251"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1601733600000">\n            <p class="match-item__summary">Delhi Capitals won by 18 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-DC">\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n                <div class="match-item__team-logo tLogo70x DC"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    228\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    210\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        8\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-KKR">\n                <div class="match-item__team-logo tLogo70x KKR"></div>\n                <p class="match-item__team-name" title="Kolkata Knight Riders">\n                    KKR\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">4</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/17"\n        class="match-item  js-match-item "\n        data-match-id="22252"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1601805600000">\n            <p class="match-item__summary">Mumbai Indians won by 34 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-MI">\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n                <div class="match-item__team-logo tLogo70x MI"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    208\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    174\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        7\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-SRH">\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/18"\n        class="match-item  js-match-item "\n        data-match-id="22253"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1601820000000">\n            <p class="match-item__summary">Chennai Super Kings won by 10 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-PBKS">\n                <p class="match-item__team-name" title="Punjab Kings">\n                    PBKS\n                </p>\n                <div class="match-item__team-logo tLogo70x PBKS"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    178\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    181\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        0\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-CSK">\n                <div class="match-item__team-logo tLogo70x CSK"></div>\n                <p class="match-item__team-name" title="Chennai Super Kings">\n                    CSK\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">5</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/19"\n        class="match-item  js-match-item "\n        data-match-id="22254"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1601906400000">\n            <p class="match-item__summary">Delhi Capitals won by 59 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-RCB">\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    137\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        9\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    196\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-DC">\n                <div class="match-item__team-logo tLogo70x DC"></div>\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">6</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/20"\n        class="match-item  js-match-item "\n        data-match-id="22255"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1601992800000">\n            <p class="match-item__summary">Mumbai Indians won by 57 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-MI">\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n                <div class="match-item__team-logo tLogo70x MI"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    193\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    136\n                </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RR">\n                <div class="match-item__team-logo tLogo70x RR"></div>\n                <p class="match-item__team-name" title="Rajasthan Royals">\n                    RR\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">7</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/21"\n        class="match-item  js-match-item "\n        data-match-id="22256"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1602079200000">\n            <p class="match-item__summary">Kolkata Knight Riders won by 10 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-KKR">\n                <p class="match-item__team-name" title="Kolkata Knight Riders">\n                    KKR\n                </p>\n                <div class="match-item__team-logo tLogo70x KKR"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    167\n                </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    157\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-CSK">\n                <div class="match-item__team-logo tLogo70x CSK"></div>\n                <p class="match-item__team-name" title="Chennai Super Kings">\n                    CSK\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">8</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/22"\n        class="match-item  js-match-item "\n        data-match-id="22257"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1602165600000">\n            <p class="match-item__summary">Sunrisers Hyderabad won by 69 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-SRH">\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    201\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    132\n                </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-PBKS">\n                <div class="match-item__team-logo tLogo70x PBKS"></div>\n                <p class="match-item__team-name" title="Punjab Kings">\n                    PBKS\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">9</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/23"\n        class="match-item  js-match-item "\n        data-match-id="22258"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1602252000000">\n            <p class="match-item__summary">Delhi Capitals won by 46 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-RR">\n                <p class="match-item__team-name" title="Rajasthan Royals">\n                    RR\n                </p>\n                <div class="match-item__team-logo tLogo70x RR"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    138\n                </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    184\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        8\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-DC">\n                <div class="match-item__team-logo tLogo70x DC"></div>\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">10</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/24"\n        class="match-item  js-match-item "\n        data-match-id="22259"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1602324000000">\n            <p class="match-item__summary">Kolkata Knight Riders won by 2 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-PBKS">\n                <p class="match-item__team-name" title="Punjab Kings">\n                    PBKS\n                </p>\n                <div class="match-item__team-logo tLogo70x PBKS"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    162\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    164\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-KKR">\n                <div class="match-item__team-logo tLogo70x KKR"></div>\n                <p class="match-item__team-name" title="Kolkata Knight Riders">\n                    KKR\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/25"\n        class="match-item  js-match-item "\n        data-match-id="22260"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1602338400000">\n            <p class="match-item__summary">Royal Challengers Bangalore won by 37 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-CSK">\n                <p class="match-item__team-name" title="Chennai Super Kings">\n                    CSK\n                </p>\n                <div class="match-item__team-logo tLogo70x CSK"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    132\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        8\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    169\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RCB">\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">11</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/26"\n        class="match-item  js-match-item "\n        data-match-id="22261"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1602410400000">\n            <p class="match-item__summary">Rajasthan Royals won by 5 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-SRH">\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    158\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    163\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RR">\n                <div class="match-item__team-logo tLogo70x RR"></div>\n                <p class="match-item__team-name" title="Rajasthan Royals">\n                    RR\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/27"\n        class="match-item  js-match-item "\n        data-match-id="22262"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1602424800000">\n            <p class="match-item__summary">Mumbai Indians won by 5 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-MI">\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n                <div class="match-item__team-logo tLogo70x MI"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    166\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    162\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-DC">\n                <div class="match-item__team-logo tLogo70x DC"></div>\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">12</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/28"\n        class="match-item  js-match-item "\n        data-match-id="22263"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1602511200000">\n            <p class="match-item__summary">Royal Challengers Bangalore won by 82 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-RCB">\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    194\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        2\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    112\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        9\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-KKR">\n                <div class="match-item__team-logo tLogo70x KKR"></div>\n                <p class="match-item__team-name" title="Kolkata Knight Riders">\n                    KKR\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">13</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/29"\n        class="match-item  js-match-item "\n        data-match-id="22264"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1602597600000">\n            <p class="match-item__summary">Chennai Super Kings won by 20 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-SRH">\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    147\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        8\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    167\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-CSK">\n                <div class="match-item__team-logo tLogo70x CSK"></div>\n                <p class="match-item__team-name" title="Chennai Super Kings">\n                    CSK\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">14</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/30"\n        class="match-item  js-match-item "\n        data-match-id="22265"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1602684000000">\n            <p class="match-item__summary">Delhi Capitals won by 13 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-DC">\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n                <div class="match-item__team-logo tLogo70x DC"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    161\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        7\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    148\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        8\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RR">\n                <div class="match-item__team-logo tLogo70x RR"></div>\n                <p class="match-item__team-name" title="Rajasthan Royals">\n                    RR\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">15</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/31"\n        class="match-item  js-match-item "\n        data-match-id="22266"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1602770400000">\n            <p class="match-item__summary">Punjab Kings won by 8 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-RCB">\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    171\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    177\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        2\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-PBKS">\n                <div class="match-item__team-logo tLogo70x PBKS"></div>\n                <p class="match-item__team-name" title="Punjab Kings">\n                    PBKS\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">16</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/32"\n        class="match-item  js-match-item "\n        data-match-id="22267"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1602856800000">\n            <p class="match-item__summary">Mumbai Indians won by 8 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-MI">\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n                <div class="match-item__team-logo tLogo70x MI"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    149\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        2\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    148\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-KKR">\n                <div class="match-item__team-logo tLogo70x KKR"></div>\n                <p class="match-item__team-name" title="Kolkata Knight Riders">\n                    KKR\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">17</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/33"\n        class="match-item  js-match-item "\n        data-match-id="22268"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1602928800000">\n            <p class="match-item__summary">Royal Challengers Bangalore won by 7 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-RR">\n                <p class="match-item__team-name" title="Rajasthan Royals">\n                    RR\n                </p>\n                <div class="match-item__team-logo tLogo70x RR"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    177\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    179\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        3\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RCB">\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/34"\n        class="match-item  js-match-item "\n        data-match-id="22269"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1602943200000">\n            <p class="match-item__summary">Delhi Capitals won by 5 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-DC">\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n                <div class="match-item__team-logo tLogo70x DC"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    185\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    179\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-CSK">\n                <div class="match-item__team-logo tLogo70x CSK"></div>\n                <p class="match-item__team-name" title="Chennai Super Kings">\n                    CSK\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">18</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/35"\n        class="match-item  js-match-item "\n        data-match-id="22270"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603015200000">\n            <p class="match-item__summary">Match tied (Kolkata Knight Riders won the Super Over)</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-SRH">\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    163\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    163\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-KKR">\n                <div class="match-item__team-logo tLogo70x KKR"></div>\n                <p class="match-item__team-name" title="Kolkata Knight Riders">\n                    KKR\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/36"\n        class="match-item  js-match-item "\n        data-match-id="22271"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603029600000">\n            <p class="match-item__summary">Match tied (Kings XI Punjab won on second Super Over)</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-MI">\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n                <div class="match-item__team-logo tLogo70x MI"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    176\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    176\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-PBKS">\n                <div class="match-item__team-logo tLogo70x PBKS"></div>\n                <p class="match-item__team-name" title="Punjab Kings">\n                    PBKS\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">19</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/37"\n        class="match-item  js-match-item "\n        data-match-id="22272"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603116000000">\n            <p class="match-item__summary">Rajasthan Royals won by 7 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-CSK">\n                <p class="match-item__team-name" title="Chennai Super Kings">\n                    CSK\n                </p>\n                <div class="match-item__team-logo tLogo70x CSK"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    125\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    126\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        3\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RR">\n                <div class="match-item__team-logo tLogo70x RR"></div>\n                <p class="match-item__team-name" title="Rajasthan Royals">\n                    RR\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">20</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/38"\n        class="match-item  js-match-item "\n        data-match-id="22273"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603202400000">\n            <p class="match-item__summary">Punjab Kings won by 5 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-PBKS">\n                <p class="match-item__team-name" title="Punjab Kings">\n                    PBKS\n                </p>\n                <div class="match-item__team-logo tLogo70x PBKS"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    167\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    164\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-DC">\n                <div class="match-item__team-logo tLogo70x DC"></div>\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">21</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/39"\n        class="match-item  js-match-item "\n        data-match-id="22274"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603288800000">\n            <p class="match-item__summary">Royal Challengers Bangalore won by 8 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-KKR">\n                <p class="match-item__team-name" title="Kolkata Knight Riders">\n                    KKR\n                </p>\n                <div class="match-item__team-logo tLogo70x KKR"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    84\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        8\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    85\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        2\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RCB">\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">22</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/40"\n        class="match-item  js-match-item "\n        data-match-id="22275"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603375200000">\n            <p class="match-item__summary">Sunrisers Hyderabad won by 8 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-RR">\n                <p class="match-item__team-name" title="Rajasthan Royals">\n                    RR\n                </p>\n                <div class="match-item__team-logo tLogo70x RR"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    154\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    156\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        2\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-SRH">\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">23</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/41"\n        class="match-item  js-match-item "\n        data-match-id="22276"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603461600000">\n            <p class="match-item__summary">Mumbai Indians won by 10 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-CSK">\n                <p class="match-item__team-name" title="Chennai Super Kings">\n                    CSK\n                </p>\n                <div class="match-item__team-logo tLogo70x CSK"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    114\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        9\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    116\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        0\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-MI">\n                <div class="match-item__team-logo tLogo70x MI"></div>\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">24</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/42"\n        class="match-item  js-match-item "\n        data-match-id="22277"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603533600000">\n            <p class="match-item__summary">Kolkata Knight Riders won by 59 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-KKR">\n                <p class="match-item__team-name" title="Kolkata Knight Riders">\n                    KKR\n                </p>\n                <div class="match-item__team-logo tLogo70x KKR"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    194\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    135\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        9\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-DC">\n                <div class="match-item__team-logo tLogo70x DC"></div>\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/43"\n        class="match-item  js-match-item "\n        data-match-id="22278"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603548000000">\n            <p class="match-item__summary">Punjab Kings won by 12 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-PBKS">\n                <p class="match-item__team-name" title="Punjab Kings">\n                    PBKS\n                </p>\n                <div class="match-item__team-logo tLogo70x PBKS"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    126\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        7\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    114\n                </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-SRH">\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">25</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/44"\n        class="match-item  js-match-item "\n        data-match-id="22279"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603620000000">\n            <p class="match-item__summary">Chennai Super Kings won by 8 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-RCB">\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    145\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    150\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        2\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-CSK">\n                <div class="match-item__team-logo tLogo70x CSK"></div>\n                <p class="match-item__team-name" title="Chennai Super Kings">\n                    CSK\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/45"\n        class="match-item  js-match-item "\n        data-match-id="22280"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603634400000">\n            <p class="match-item__summary">Rajasthan Royals won by 8 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-RR">\n                <p class="match-item__team-name" title="Rajasthan Royals">\n                    RR\n                </p>\n                <div class="match-item__team-logo tLogo70x RR"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    196\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        2\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    195\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-MI">\n                <div class="match-item__team-logo tLogo70x MI"></div>\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">26</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/46"\n        class="match-item  js-match-item "\n        data-match-id="22281"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603720800000">\n            <p class="match-item__summary">Punjab Kings won by 8 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-KKR">\n                <p class="match-item__team-name" title="Kolkata Knight Riders">\n                    KKR\n                </p>\n                <div class="match-item__team-logo tLogo70x KKR"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    149\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        9\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    150\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        2\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-PBKS">\n                <div class="match-item__team-logo tLogo70x PBKS"></div>\n                <p class="match-item__team-name" title="Punjab Kings">\n                    PBKS\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">27</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/47"\n        class="match-item  js-match-item "\n        data-match-id="22282"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603807200000">\n            <p class="match-item__summary">Sunrisers Hyderabad won by 88 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-SRH">\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    219\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        2\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    131\n                </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-DC">\n                <div class="match-item__team-logo tLogo70x DC"></div>\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">28</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/48"\n        class="match-item  js-match-item "\n        data-match-id="22283"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603893600000">\n            <p class="match-item__summary">Mumbai Indians won by 5 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-MI">\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n                <div class="match-item__team-logo tLogo70x MI"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    166\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    164\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RCB">\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">29</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/49"\n        class="match-item  js-match-item "\n        data-match-id="22284"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1603980000000">\n            <p class="match-item__summary">Chennai Super Kings won by 6 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-CSK">\n                <p class="match-item__team-name" title="Chennai Super Kings">\n                    CSK\n                </p>\n                <div class="match-item__team-logo tLogo70x CSK"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    178\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    172\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-KKR">\n                <div class="match-item__team-logo tLogo70x KKR"></div>\n                <p class="match-item__team-name" title="Kolkata Knight Riders">\n                    KKR\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">30</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/50"\n        class="match-item  js-match-item "\n        data-match-id="22285"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1604066400000">\n            <p class="match-item__summary">Rajasthan Royals won by 7 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-PBKS">\n                <p class="match-item__team-name" title="Punjab Kings">\n                    PBKS\n                </p>\n                <div class="match-item__team-logo tLogo70x PBKS"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    185\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    186\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        3\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RR">\n                <div class="match-item__team-logo tLogo70x RR"></div>\n                <p class="match-item__team-name" title="Rajasthan Royals">\n                    RR\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Oct</span>\n                            <span class="match-scroller__day">31</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/51"\n        class="match-item  js-match-item "\n        data-match-id="22286"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1604138400000">\n            <p class="match-item__summary">Mumbai Indians won by 9 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-DC">\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n                <div class="match-item__team-logo tLogo70x DC"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    110\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        9\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    111\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        1\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-MI">\n                <div class="match-item__team-logo tLogo70x MI"></div>\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/52"\n        class="match-item  js-match-item "\n        data-match-id="22287"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1604152800000">\n            <p class="match-item__summary">Sunrisers Hyderabad won by 5 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-RCB">\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_B_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    120\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        7\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    121\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-SRH">\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Nov</span>\n                            <span class="match-scroller__day">1</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/53"\n        class="match-item  js-match-item "\n        data-match-id="22288"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1604224800000">\n            <p class="match-item__summary">Chennai Super Kings won by 9 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-CSK">\n                <p class="match-item__team-name" title="Chennai Super Kings">\n                    CSK\n                </p>\n                <div class="match-item__team-logo tLogo70x CSK"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    154\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        1\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    153\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        6\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-PBKS">\n                <div class="match-item__team-logo tLogo70x PBKS"></div>\n                <p class="match-item__team-name" title="Punjab Kings">\n                    PBKS\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/54"\n        class="match-item  js-match-item "\n        data-match-id="22289"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1604239200000">\n            <p class="match-item__summary">Kolkata Knight Riders won by 60 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-KKR">\n                <p class="match-item__team-name" title="Kolkata Knight Riders">\n                    KKR\n                </p>\n                <div class="match-item__team-logo tLogo70x KKR"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    191\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        7\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    131\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        9\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RR">\n                <div class="match-item__team-logo tLogo70x RR"></div>\n                <p class="match-item__team-name" title="Rajasthan Royals">\n                    RR\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Nov</span>\n                            <span class="match-scroller__day">2</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/55"\n        class="match-item  js-match-item "\n        data-match-id="22290"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1604325600000">\n            <p class="match-item__summary">Delhi Capitals won by 6 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-DC">\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n                <div class="match-item__team-logo tLogo70x DC"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    154\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    152\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        7\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RCB">\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Nov</span>\n                            <span class="match-scroller__day">3</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/56"\n        class="match-item  js-match-item "\n        data-match-id="22291"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1604412000000">\n            <p class="match-item__summary">Sunrisers Hyderabad won by 10 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-SRH">\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    151\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        0\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    149\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        8\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-MI">\n                <div class="match-item__team-logo tLogo70x MI"></div>\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Nov</span>\n                            <span class="match-scroller__day">5</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/57"\n        class="match-item  js-match-item "\n        data-match-id="22359"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1604584800000">\n            <p class="match-item__summary">Mumbai Indians won by 57 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-MI">\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n                <div class="match-item__team-logo tLogo70x MI"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    200\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    143\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        8\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-DC">\n                <div class="match-item__team-logo tLogo70x DC"></div>\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Nov</span>\n                            <span class="match-scroller__day">6</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/58"\n        class="match-item  js-match-item "\n        data-match-id="22360"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1604671200000">\n            <p class="match-item__summary">Sunrisers Hyderabad won by 6 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-SRH">\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    132\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        4\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    131\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        7\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-RCB">\n                <div class="match-item__team-logo tLogo70x RCB"></div>\n                <p class="match-item__team-name" title="Royal Challengers Bangalore">\n                    RCB\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Nov</span>\n                            <span class="match-scroller__day">8</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/59"\n        class="match-item  js-match-item "\n        data-match-id="22361"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1604844000000">\n            <p class="match-item__summary">Delhi Capitals won by 17 runs</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-DC">\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n                <div class="match-item__team-logo tLogo70x DC"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    189\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        3\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    172\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        8\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-SRH">\n                <div class="match-item__team-logo tLogo70x SRH"></div>\n                <p class="match-item__team-name" title="Sunrisers Hyderabad">\n                    SRH\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n\n                        <h2 class="match-scroller__date">\n                            <span class="match-scroller__month">Nov</span>\n                            <span class="match-scroller__day">10</span>\n                        </h2>\n                    <li class="match-scroller__item">\n\n\n    <a href="/match/2020/60"\n        class="match-item  js-match-item "\n        data-match-id="22362"\n        data-tournament-id="18790"\n        data-match-state="C"\n        data-timestamp="1605016800000">\n            <p class="match-item__summary">Mumbai Indians won by 5 wickets</p>\n        <div class="match-item__content">\n            <div class="match-item__team match-item__team--a t-MI">\n                <p class="match-item__team-name" title="Mumbai Indians">\n                    MI\n                </p>\n                <div class="match-item__team-logo tLogo70x MI"></div>\n            </div>\n\n                <div class="match-item__scorebox">\n                        <!-- TEAM_A_WON -->\n    <span class="match-item__score match-item__score--a">\n                <span class="match-item__score--runs">\n                    157\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        5\n                    </span>\n    </span>\n                    <span class="match-item__versus">V</span>\n    <span class="match-item__score match-item__score--b">\n                <span class="match-item__score--runs">\n                    156\n                </span>\n                    <span class="match-item__score--delimiter">/</span>\n                    <span class="match-item__score--wkts">\n                        7\n                    </span>\n    </span>\n                </div>\n\n            <div class="match-item__team match-item__team--b t-DC">\n                <div class="match-item__team-logo tLogo70x DC"></div>\n                <p class="match-item__team-name" title="Delhi Capitals">\n                    DC\n                </p>\n            </div>\n        </div>\n    </a>\n                    </li>\n        </ul>\n    </section>\n</div>\n\n</section>\n\n\n    <!-- Script includes -->\n    <script src="/resources/v4.19.2/scripts/vendors.min.js"></script>\n    \n    <script src="/resources/v4.19.2/scripts/main.min.js"></script>\n    <script src="/resources/v4.19.2/widgets/common.min.js"></script>\n</body>\n</html>'
    


```python
data.close() #to close the data
```

### Parsing


```python
from bs4 import BeautifulSoup as soup
```


```python
my_soup=soup(html,'html.parser') #html.parser is used because we are parsing a html file
#,if it was a json file we would have used json.parser
```


```python
print(my_soup)
```

    <!DOCTYPE html>
    
    <html lang="en">
    <head>
    <meta content="IPLT20.com - Indian Premier League Official Website" name="twitter:title"/>
    <meta content="ipl, iplt20, indian premier league, ipl cricket, ipl match, ipl live, ipl score, ipl scorecard, ipl stats, ipl schedule, ipl results, ipl points table, ipl teams, ipl videos, ipl teams, ipl news, BCCI IPL" name="keywords"/>
    <meta content="website" property="og:type"/>
    <meta content="Visit IPLT20.com the official IPLT20 website for minute-to-minute LIVE updates." name="description"/>
    <meta content="Visit IPLT20.com the official IPLT20 website for minute-to-minute LIVE updates." name="twitter:description"/>
    <meta content="IPLT20.com - Indian Premier League Official Website" property="og:title"/>
    <title>IPLT20.com - Indian Premier League Official Website</title>
    <meta content="Visit IPLT20.com the official IPLT20 website for minute-to-minute LIVE updates." property="og:description"/>
    <meta charset="utf-8"/>
    <meta content="width=device-width, initial-scale=1" name="viewport"/>
    <meta content="app-id=509837419" name="apple-itunes-app"/>
    <meta content="#263973" name="theme-color"/>
    <link href="/resources/v4.19.2/i/elements/favicon.ico" rel="shortcut icon"/>
    <script>window.RESOURCES_VERSION = 'v4.19.2'</script>
    <!-- Service Worker Registration -->
    <script>"serviceWorker"in navigator&&window.addEventListener("load",function(){navigator.serviceWorker.register("/sw.js?resourcesPath=v4.19.2").then(function(e){console.log("ServiceWorker successfully registered with scope: ",e.scope)},function(e){console.error("ServiceWorker registration failed: ",e)})});</script>
    <!-- Service Worker Registration -->
    <script>"serviceWorker"in navigator&&window.addEventListener("load",function(){navigator.serviceWorker.register("/sw.js?resourcesPath=v4.19.2").then(function(e){console.log("ServiceWorker successfully registered with scope: ",e.scope)},function(e){console.error("ServiceWorker registration failed: ",e)})});</script>
    <link as="font" crossorigin="" href="/resources/v4.19.2/fonts/SourceSansPro-Light.ttf" rel="preload"/>
    <link as="font" crossorigin="" href="/resources/v4.19.2/fonts/SourceSansPro-Regular.ttf" rel="preload"/>
    <link as="font" crossorigin="" href="/resources/v4.19.2/fonts/SourceSansPro-SemiBold.ttf" rel="preload"/>
    <link as="font" crossorigin="" href="/resources/v4.19.2/fonts/SourceSansPro-Bold.ttf" rel="preload"/>
    <link as="font" crossorigin="" href="/resources/v4.19.2/fonts/SourceSansPro-Black.ttf" rel="preload"/>
    <link href="/resources/v4.19.2/styles/screen.css" rel="stylesheet">
    </link></head>
    <body class="t-generic">
    <script>
    	(function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
    	(i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
    	m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
    	})(window,document,'script','//www.google-analytics.com/analytics.js','ga');
    	
    	ga('create', 'UA-11525770-1', 'auto');
    	ga('send', 'pageview');
    	
    </script>
    <div class="top-bar">
    <ul class="inline-list top-bar__tournament-info">
    <li class="inline-list__item top-bar__tournament-info-item--bold">VIVO IPL 2021</li>
    </ul>
    <ul class="inline-list top-bar__logos">
    <li class="inline-list__item has-link">
    <a class="top-bar-link bcci" href="http://www.bcci.tv/">BCCI.tv</a>
    </li>
    </ul>
    <ul class="inline-list top-bar__social">
    <li class="inline-list__item">Follow IPL</li>
    <li class="inline-list__item has-link">
    <a class="facebook" href="//www.facebook.com/ipl" rel="noopener" target="_blank">
    <svg class="icon">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-facebook" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    <span class="u-screen-reader">Facebook</span>
    </a>
    </li>
    <li class="inline-list__item has-link">
    <a class="instagram" href="//www.instagram.com/iplt20">
    <svg class="icon">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-instagram" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    <span class="u-screen-reader">Instagram</span>
    </a>
    </li>
    <li class="inline-list__item has-link">
    <a class="twitter" href="//twitter.com/IPL" rel="noopener" target="_blank">
    <svg class="icon">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-twitter" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    <span class="u-screen-reader">Twitter</span>
    </a>
    </li>
    </ul>
    </div>
    <header class="js-main-nav page-header" data-script="ipl_global-header" data-widget="main-nav" role="banner">
    <div class="js-sticky">
    <div class="page-header__menu-wrapper">
    <div class="page-header__logo-container">
    <a class="page-header__logo" href="/">Indian Premier League</a>
    </div>
    <nav class="main-nav" role="navigation">
    <div class="main-nav__menu-container">
    <div class="main-nav__mobile-strip u-show-desktop">
    <span class="main-nav__mobile-strip-text">VIVO IPL 2021</span>
    </div>
    <div class="main-nav__menu-container-inner js-main-menu">
    <ul class="main-nav__menu">
    <li class="main-nav__menu-item u-show-desktop">
    <a class="main-nav__link" href="/">
                    Home
                </a>
    </li>
    <li class="main-nav__menu-item">
    <div class="main-nav__link main-nav__link--has-drop-down js-navigation-link">
                    Matches
    	<svg class="icon main-nav__chevron-down">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-down" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    </div>
    <div class="main-nav__drop-down nav-drop-down nav-drop-down--reveal-on-hover" tabindex="0">
    <div class="nav-drop-down__options">
    <svg class="icon nav-drop-down__options-dropdown-arrow">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-arrow-block-up" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    <ul>
    <li class="nav-drop-down__option" data-label="Results">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/matches/results/men/2020">
                                    Results
                                </a>
    </li>
    </ul>
    </div>
    </div></li>
    <li class="main-nav__menu-item">
    <div class="main-nav__link main-nav__link--has-drop-down js-navigation-link">
                    Videos
    	<svg class="icon main-nav__chevron-down">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-down" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    </div>
    <div class="main-nav__drop-down nav-drop-down nav-drop-down--reveal-on-hover" tabindex="0">
    <div class="nav-drop-down__options">
    <svg class="icon nav-drop-down__options-dropdown-arrow">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-arrow-block-up" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    <ul>
    <li class="nav-drop-down__option" data-label="Video Hub">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/video">
                                    Video Hub
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Highlights">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/video/highlights">
                                    Highlights
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Magic Moments">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/video/magic-moments">
                                    Magic Moments
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Interviews">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/video/interviews">
                                    Interviews
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Press Conferences">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/video/press-conferences">
                                    Press Conferences
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="All Videos">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/video/all">
                                    All Videos
                                </a>
    </li>
    </ul>
    </div>
    </div></li>
    <li class="main-nav__menu-item is-active">
    <a class="main-nav__link is-active" href="/points-table">
                    Points Table
                </a>
    </li>
    <li class="main-nav__menu-item">
    <div class="main-nav__link main-nav__link--has-drop-down js-navigation-link">
                    Stats
    	<svg class="icon main-nav__chevron-down">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-down" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    </div>
    <div class="main-nav__drop-down nav-drop-down nav-drop-down--reveal-on-hover" tabindex="0">
    <div class="nav-drop-down__options">
    <svg class="icon nav-drop-down__options-dropdown-arrow">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-arrow-block-up" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    <ul>
    <li class="nav-drop-down__option" data-label="By Season">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/stats/2020">
                                    By Season
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="All Time">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/stats/all-time">
                                    All Time
                                </a>
    </li>
    </ul>
    </div>
    </div></li>
    <li class="main-nav__menu-item">
    <a class="main-nav__link" href="/auction">
                    Auction
                </a>
    </li>
    <li class="main-nav__menu-item">
    <div class="main-nav__link main-nav__link--has-drop-down js-navigation-link">
                    Teams
    	<svg class="icon main-nav__chevron-down">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-down" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    </div>
    <div class="main-nav__drop-down nav-drop-down nav-drop-down--reveal-on-hover" tabindex="0">
    <div class="nav-drop-down__options">
    <svg class="icon nav-drop-down__options-dropdown-arrow">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-arrow-block-up" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    <ul>
    <li class="nav-drop-down__option" data-label="Chennai Super Kings">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/teams/chennai-super-kings">
                                    Chennai Super Kings
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Delhi Capitals">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/teams/delhi-capitals">
                                    Delhi Capitals
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Kolkata Knight Riders">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/teams/kolkata-knight-riders">
                                    Kolkata Knight Riders
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Mumbai Indians">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/teams/mumbai-indians">
                                    Mumbai Indians
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Punjab Kings">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/teams/punjab-kings">
                                    Punjab Kings
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Rajasthan Royals">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/teams/rajasthan-royals">
                                    Rajasthan Royals
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Royal Challengers Bangalore">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/teams/royal-challengers-bangalore">
                                    Royal Challengers Bangalore
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Sunrisers Hyderabad">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/teams/sunrisers-hyderabad">
                                    Sunrisers Hyderabad
                                </a>
    </li>
    </ul>
    </div>
    </div></li>
    <li class="main-nav__menu-item">
    <div class="main-nav__link main-nav__link--has-drop-down js-navigation-link">
                    News
    	<svg class="icon main-nav__chevron-down">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-down" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    </div>
    <div class="main-nav__drop-down nav-drop-down nav-drop-down--reveal-on-hover" tabindex="0">
    <div class="nav-drop-down__options">
    <svg class="icon nav-drop-down__options-dropdown-arrow">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-arrow-block-up" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    <ul>
    <li class="nav-drop-down__option" data-label="All News">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/news">
                                    All News
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Announcements">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/news/announcements">
                                    Announcements
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Match Reports">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/news/match-reports">
                                    Match Reports
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Features &amp; Interviews">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/news/features-and-interviews">
                                    Features &amp; Interviews
                                </a>
    </li>
    </ul>
    </div>
    </div></li>
    <li class="main-nav__menu-item">
    <div class="main-nav__link main-nav__link--has-drop-down js-navigation-link">
                    More
    	<svg class="icon main-nav__chevron-down">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-down" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    </div>
    <div class="main-nav__drop-down nav-drop-down nav-drop-down--reveal-on-hover" tabindex="0">
    <div class="nav-drop-down__options">
    <svg class="icon nav-drop-down__options-dropdown-arrow">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-arrow-block-up" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    <ul>
    <li class="nav-drop-down__option" data-label="About">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/about">
                                    About
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Fantasy">
    <a class="main-nav__link main-nav__link--in-drop-down" href="//fantasy.iplt20.com">
                                    Fantasy
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Mobile Products">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/mobile">
                                    Mobile Products
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Photos">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/photos">
                                    Photos
                                </a>
    </li>
    <li class="nav-drop-down__option" data-label="Venues">
    <a class="main-nav__link main-nav__link--in-drop-down" href="/venues">
                                    Venues
                                </a>
    </li>
    </ul>
    </div>
    </div></li>
    </ul>
    </div>
    </div>
    <div class="nav-footer">
    <ul class="inline-list nav-footer__buttons nav-footer__buttons">
    <li class="inline-list__item col-6 has-link">
    <a class="btn btn--dark-blue" href="//www.bcci.tv" rel="noopener" target="_blank">BCCI.tv</a>
    </li>
    <li class="inline-list__item col-6 has-link">
    <a class="btn btn--dark-blue" href="/">iplt20.com</a>
    </li>
    </ul>
    <ul class="inline-list nav-footer__social social-list">
    <li class="inline-list__item social-list__label">Follow us</li>
    <li class="inline-list__item">
    <a class="facebook" href="//facebook.com/ipl" rel="noopener" target="_blank">
    <svg class="icon">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-facebook" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    <span class="u-screen-reader">Facebook</span>
    </a>
    </li>
    <li class="inline-list__item">
    <a class="instagram" href="//instagram.com/iplt20" rel="noopener" target="_blank">
    <svg class="icon">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-instagram" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    <span class="u-screen-reader">Instagram</span>
    </a>
    </li>
    <li class="inline-list__item">
    <a class="twitter" href="//twitter.com/IPL" rel="noopener" target="_blank">
    <svg class="icon">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-twitter" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    <span class="u-screen-reader">Twitter</span>
    </a>
    </li>
    </ul>
    </div>
    </nav>
    <div class="site-search">
    <button aria-label="Search" class="site-search__btn js-search-btn">
    <i class="site-search__btn-icon"></i>
    </button>
    <div class="pulse-poll-btn-wrapper">
    <button class="pulse-poll-btn js-poll-btn">
    <span class="pulse-poll-btn__num"></span>
    <svg class="icon pulse-poll-btn__icon">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-pulse" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    <span class="pulse-poll-btn__label">Fan <br/> Poll</span>
    </button>
    </div>
    <button class="burger js-burger">
    <div class="burger__icon">
    <span></span><span></span><span></span><span></span>
    </div>
    <span class="u-screen-reader">Close mobile menu</span>
    </button>
    </div>
    </div>
    <form action="/search" class="site-search-form js-form" type="GET">
    <div class="wrapper wrapper--small site-search-form__container">
    <input aria-label="Search" class="site-search-form__search-box js-search-input" name="term" placeholder="Search" type="text"/>
    <div class="search__go">
    <input class="site-search-form__btn js-search-button" type="submit"/>
    <svg class="icon">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-search" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    </div>
    </div>
    </form>
    </div>
    <div class="mcContentOverlay"></div>
    <div class="pulsePoll" data-script="ipl_poll" data-season="ipl2020" data-widget="poll">
    <header>
    <div class="pulseIcon"></div>
    <h4>Fan Poll</h4>
    <a class="pulseButton close"><span></span></a>
    <a class="pulseButton back"><span></span></a>
    </header>
    <ul class="contentSlider pulseSlide">
    <!-- Pulse  question -->
    <li class="slide questions contentSlide" data-view="question-list">
    <div class="slideContent">
    <div class="title">OPEN QUESTIONS</div>
    <div class="empty" style="">There are currently no open questions.</div>
    <ul class="questionList"></ul>
    <div class="options">
    <a class="historyBtn voting-history-button">Voting History<span></span></a>
    </div>
    </div>
    </li>
    <!-- Pulse  Q&A -->
    <li class="slide question contentSlide" data-view="question">
    <div class="slideContent questionContainer"></div>
    <div class="pulseHistory" style="display: none;">
    <div class="historyResults slideContent answerContainer" style="display: none;"></div>
    <div class="questionsList slideContent" style="display:none;">
    <ul class=""></ul>
    </div>
    <div class="empty-state slideContent" style="">
    <div class="title">Voting History</div>
    <p>A breakdown of the questions you voted on will appear here.</p>
    </div>
    </div>
    </li>
    </ul>
    </div><!-- END pulsePoll -->
    </header>
    <div class="js-app-promo mobile-banner" data-script="ipl_app-promo" data-widget="app-promo">
    <div data-widget="lazy-load-images">
    <div class="wrapper">
    <p class="header">IPL on the Go</p>
    <p class="subHeader">Get all the IPL action at your fingertips</p>
    <div class="app-buttons">
    <a class="app-button apple" href="https://itunes.apple.com/in/app/iplt20/id509837419?ls=1&amp;mt=8" rel="noopener" target="_blank"></a>
    <a class="app-button android" href="https://play.google.com/store/apps/details?id=com.pulselive.bcci.android&amp;hl=en" rel="noopener" target="_blank"></a>
    </div>
    <div class="js-lazy-load u-observed img" data-alt="Top of page pushdown promo" data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2020/09/08/f74495c2-8feb-4efb-be7e-d78f03eac47b/Top-of-page-pushdown-promo.png?height=133&amp;width=400" data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/08/f74495c2-8feb-4efb-be7e-d78f03eac47b/Top-of-page-pushdown-promo.png?height=266&amp;width=800" data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2020/09/08/f74495c2-8feb-4efb-be7e-d78f03eac47b/Top-of-page-pushdown-promo.png?height=133&amp;width=400" data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/08/f74495c2-8feb-4efb-be7e-d78f03eac47b/Top-of-page-pushdown-promo.png?height=266&amp;width=800" data-object-fit="false" data-picture-in-view="false">
    </div>
    <button aria-label="Close" class="mobile-banner__close js-app-promo-close"></button>
    </div>
    </div>
    </div>
    <header class="page-heading">
    <div class="page-heading__background">
    <img aria-hidden="true" class="branding-asset page-heading__background-image" src="/resources/v4.19.2/i/element-bgs/ipl_svg_background_2020-t-generic.svg"/>
    </div>
    <div class="page-heading__content">
    <h1 class="page-heading__title"> Points <span class="widget__title--bold">Table</span></h1>
    </div>
    </header>
    <main id="main-content" tabindex="0">
    <div class="wrapper" data-script="ipl_dropdown" data-widget="dropdown-link">
    <div class="drop-down--heading drop-down drop-down--link js-drop-down js-season-dropdown">
    <div aria-label="Select a Season" class="drop-down__clickzone js-dropdown-trigger" role="button" tabindex="0"></div>
    <div class="drop-down__label js-drop-down-label">Select a Season</div>
    <div class="drop-down__current js-drop-down-current">2020 Season</div>
    <ul class="drop-down__dropdown-list js-drop-down-options">
    <li class="drop-down__dropdown-list__option" data-option="0" role="button" tabindex="0">
    <a class="drop-down__link" href="/points-table/2020">
                            2020
                        </a>
    </li>
    <li class="drop-down__dropdown-list__option" data-option="1" role="button" tabindex="0">
    <a class="drop-down__link" href="/points-table/2019">
                                    2019
                                </a>
    </li>
    <li class="drop-down__dropdown-list__option" data-option="2" role="button" tabindex="0">
    <a class="drop-down__link" href="/points-table/2018">
                                    2018
                                </a>
    </li>
    <li class="drop-down__dropdown-list__option" data-option="3" role="button" tabindex="0">
    <a class="drop-down__link" href="/points-table/2017">
                                    2017
                                </a>
    </li>
    <li class="drop-down__dropdown-list__option" data-option="4" role="button" tabindex="0">
    <a class="drop-down__link" href="/points-table/2016">
                                    2016
                                </a>
    </li>
    <li class="drop-down__dropdown-list__option" data-option="5" role="button" tabindex="0">
    <a class="drop-down__link" href="/points-table/2015">
                                    2015
                                </a>
    </li>
    <li class="drop-down__dropdown-list__option" data-option="6" role="button" tabindex="0">
    <a class="drop-down__link" href="/points-table/2014">
                                    2014
                                </a>
    </li>
    <li class="drop-down__dropdown-list__option" data-option="7" role="button" tabindex="0">
    <a class="drop-down__link" href="/points-table/2013">
                                    2013
                                </a>
    </li>
    <li class="drop-down__dropdown-list__option" data-option="8" role="button" tabindex="0">
    <a class="drop-down__link" href="/points-table/2012">
                                    2012
                                </a>
    </li>
    <li class="drop-down__dropdown-list__option" data-option="9" role="button" tabindex="0">
    <a class="drop-down__link" href="/points-table/2011">
                                    2011
                                </a>
    </li>
    <li class="drop-down__dropdown-list__option" data-option="11" role="button" tabindex="0">
    <a class="drop-down__link" href="/points-table/2010">
                                    2010
                                </a>
    </li>
    <li class="drop-down__dropdown-list__option" data-option="12" role="button" tabindex="0">
    <a class="drop-down__link" href="/points-table/2009">
                                    2009
                                </a>
    </li>
    <li class="drop-down__dropdown-list__option" data-option="10" role="button" tabindex="0">
    <a class="drop-down__link" href="/points-table/2008">
                                    2008
                                </a>
    </li>
    </ul>
    </div>
    <table class="standings-table standings-table--full">
    <tr class="standings-table__header">
    <th class="standings-table__freeze"></th>
    <th class="u-left-text standings-table__freeze">Team</th>
    <th class="standings-table__padded">Pld</th>
    <th class="standings-table__optional">Won</th>
    <th class="standings-table__optional">Lost</th>
    <th class="standings-table__optional">Tied</th>
    <th class="standings-table__optional">N/R</th>
    <th>Net RR</th>
    <th class="standings-table__optional">For</th>
    <th class="standings-table__optional">Against</th>
    <th>Pts</th>
    <th>Form</th>
    </tr>
    <tr>
    <td class="standings-table__qualified standings-table__freeze u-text-center">Q</td>
    <td class="standings-table__team standings-table__freeze">
    <i class="table__logo tLogo40x32 MI"></i>
    <a href="/teams/mumbai-indians">
    <span class="standings-table__team-name js-team">Mumbai Indians</span>
    <span class="standings-table__team-name standings-table__team-name--short js-team">MI</span>
    </a>
    </td>
    <td class="standings-table__padded">14</td>
    <td class="standings-table__optional">9</td>
    <td class="standings-table__optional">5</td>
    <td class="standings-table__optional">0</td>
    <td class="standings-table__optional">0</td>
    <td>+1.107</td>
    <td class="standings-table__optional">2,378/262.2</td>
    <td class="standings-table__optional">2,187/274.5</td>
    <td class="standings-table__highlight js-points">18</td>
    <td> <ul class="standings-table__form">
    <li class="standings-table__outcome standings-table__outcome--win standings-table__optional">W</li>
    <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>
    <li class="standings-table__outcome standings-table__outcome--win">W</li>
    <li class="standings-table__outcome standings-table__outcome--win">W</li>
    <li class="standings-table__outcome standings-table__outcome--loss">L</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td class="standings-table__qualified standings-table__freeze u-text-center">Q</td>
    <td class="standings-table__team standings-table__freeze">
    <i class="table__logo tLogo40x32 DC"></i>
    <a href="/teams/delhi-capitals">
    <span class="standings-table__team-name js-team">Delhi Capitals</span>
    <span class="standings-table__team-name standings-table__team-name--short js-team">DC</span>
    </a>
    </td>
    <td class="standings-table__padded">14</td>
    <td class="standings-table__optional">8</td>
    <td class="standings-table__optional">6</td>
    <td class="standings-table__optional">0</td>
    <td class="standings-table__optional">0</td>
    <td>-0.109</td>
    <td class="standings-table__optional">2,289/278.5</td>
    <td class="standings-table__optional">2,271/273</td>
    <td class="standings-table__highlight js-points">16</td>
    <td> <ul class="standings-table__form">
    <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>
    <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>
    <li class="standings-table__outcome standings-table__outcome--loss">L</li>
    <li class="standings-table__outcome standings-table__outcome--loss">L</li>
    <li class="standings-table__outcome standings-table__outcome--win">W</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td class="standings-table__qualified standings-table__freeze u-text-center">Q</td>
    <td class="standings-table__team standings-table__freeze">
    <i class="table__logo tLogo40x32 SRH"></i>
    <a href="/teams/sunrisers-hyderabad">
    <span class="standings-table__team-name js-team">Sunrisers Hyderabad</span>
    <span class="standings-table__team-name standings-table__team-name--short js-team">SRH</span>
    </a>
    </td>
    <td class="standings-table__padded">14</td>
    <td class="standings-table__optional">7</td>
    <td class="standings-table__optional">7</td>
    <td class="standings-table__optional">0</td>
    <td class="standings-table__optional">0</td>
    <td>+0.608</td>
    <td class="standings-table__optional">2,225/269.3</td>
    <td class="standings-table__optional">2,125/277.5</td>
    <td class="standings-table__highlight js-points">14</td>
    <td> <ul class="standings-table__form">
    <li class="standings-table__outcome standings-table__outcome--win standings-table__optional">W</li>
    <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>
    <li class="standings-table__outcome standings-table__outcome--win">W</li>
    <li class="standings-table__outcome standings-table__outcome--win">W</li>
    <li class="standings-table__outcome standings-table__outcome--win">W</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td class="standings-table__qualified standings-table__freeze u-text-center">Q</td>
    <td class="standings-table__team standings-table__freeze">
    <i class="table__logo tLogo40x32 RCB"></i>
    <a href="/teams/royal-challengers-bangalore">
    <span class="standings-table__team-name js-team">Royal Challengers Bangalore</span>
    <span class="standings-table__team-name standings-table__team-name--short js-team">RCB</span>
    </a>
    </td>
    <td class="standings-table__padded">14</td>
    <td class="standings-table__optional">7</td>
    <td class="standings-table__optional">7</td>
    <td class="standings-table__optional">0</td>
    <td class="standings-table__optional">0</td>
    <td>-0.172</td>
    <td class="standings-table__optional">2,147/272.2</td>
    <td class="standings-table__optional">2,183/271</td>
    <td class="standings-table__highlight js-points">14</td>
    <td> <ul class="standings-table__form">
    <li class="standings-table__outcome standings-table__outcome--win standings-table__optional">W</li>
    <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>
    <li class="standings-table__outcome standings-table__outcome--loss">L</li>
    <li class="standings-table__outcome standings-table__outcome--loss">L</li>
    <li class="standings-table__outcome standings-table__outcome--loss">L</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td class="standings-table__freeze u-text-center">5</td>
    <td class="standings-table__team standings-table__freeze">
    <i class="table__logo tLogo40x32 KKR"></i>
    <a href="/teams/kolkata-knight-riders">
    <span class="standings-table__team-name js-team">Kolkata Knight Riders</span>
    <span class="standings-table__team-name standings-table__team-name--short js-team">KKR</span>
    </a>
    </td>
    <td class="standings-table__padded">14</td>
    <td class="standings-table__optional">7</td>
    <td class="standings-table__optional">7</td>
    <td class="standings-table__optional">0</td>
    <td class="standings-table__optional">0</td>
    <td>-0.214</td>
    <td class="standings-table__optional">2,219/278</td>
    <td class="standings-table__optional">2,206/269.1</td>
    <td class="standings-table__highlight js-points">14</td>
    <td> <ul class="standings-table__form">
    <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>
    <li class="standings-table__outcome standings-table__outcome--win standings-table__optional">W</li>
    <li class="standings-table__outcome standings-table__outcome--loss">L</li>
    <li class="standings-table__outcome standings-table__outcome--loss">L</li>
    <li class="standings-table__outcome standings-table__outcome--win">W</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td class="standings-table__freeze u-text-center">6</td>
    <td class="standings-table__team standings-table__freeze">
    <i class="table__logo tLogo40x32 PBKS"></i>
    <a href="/teams/punjab-kings">
    <span class="standings-table__team-name js-team">Punjab Kings</span>
    <span class="standings-table__team-name standings-table__team-name--short js-team">PBKS</span>
    </a>
    </td>
    <td class="standings-table__padded">14</td>
    <td class="standings-table__optional">6</td>
    <td class="standings-table__optional">8</td>
    <td class="standings-table__optional">0</td>
    <td class="standings-table__optional">0</td>
    <td>-0.162</td>
    <td class="standings-table__optional">2,335/277.5</td>
    <td class="standings-table__optional">2,343/273.3</td>
    <td class="standings-table__highlight js-points">12</td>
    <td> <ul class="standings-table__form">
    <li class="standings-table__outcome standings-table__outcome--win standings-table__optional">W</li>
    <li class="standings-table__outcome standings-table__outcome--win standings-table__optional">W</li>
    <li class="standings-table__outcome standings-table__outcome--win">W</li>
    <li class="standings-table__outcome standings-table__outcome--loss">L</li>
    <li class="standings-table__outcome standings-table__outcome--loss">L</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td class="standings-table__freeze u-text-center">7</td>
    <td class="standings-table__team standings-table__freeze">
    <i class="table__logo tLogo40x32 CSK"></i>
    <a href="/teams/chennai-super-kings">
    <span class="standings-table__team-name js-team">Chennai Super Kings</span>
    <span class="standings-table__team-name standings-table__team-name--short js-team">CSK</span>
    </a>
    </td>
    <td class="standings-table__padded">14</td>
    <td class="standings-table__optional">6</td>
    <td class="standings-table__optional">8</td>
    <td class="standings-table__optional">0</td>
    <td class="standings-table__optional">0</td>
    <td>-0.455</td>
    <td class="standings-table__optional">2,191/274.3</td>
    <td class="standings-table__optional">2,275/269.4</td>
    <td class="standings-table__highlight js-points">12</td>
    <td> <ul class="standings-table__form">
    <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>
    <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>
    <li class="standings-table__outcome standings-table__outcome--win">W</li>
    <li class="standings-table__outcome standings-table__outcome--win">W</li>
    <li class="standings-table__outcome standings-table__outcome--win">W</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td class="standings-table__freeze u-text-center">8</td>
    <td class="standings-table__team standings-table__freeze">
    <i class="table__logo tLogo40x32 RR"></i>
    <a href="/teams/rajasthan-royals">
    <span class="standings-table__team-name js-team">Rajasthan Royals</span>
    <span class="standings-table__team-name standings-table__team-name--short js-team">RR</span>
    </a>
    </td>
    <td class="standings-table__padded">14</td>
    <td class="standings-table__optional">6</td>
    <td class="standings-table__optional">8</td>
    <td class="standings-table__optional">0</td>
    <td class="standings-table__optional">0</td>
    <td>-0.569</td>
    <td class="standings-table__optional">2,288/272.4</td>
    <td class="standings-table__optional">2,482/277</td>
    <td class="standings-table__highlight js-points">12</td>
    <td> <ul class="standings-table__form">
    <li class="standings-table__outcome standings-table__outcome--win standings-table__optional">W</li>
    <li class="standings-table__outcome standings-table__outcome--loss standings-table__optional">L</li>
    <li class="standings-table__outcome standings-table__outcome--win">W</li>
    <li class="standings-table__outcome standings-table__outcome--win">W</li>
    <li class="standings-table__outcome standings-table__outcome--loss">L</li>
    </ul>
    </td>
    </tr>
    </table>
    </div>
    </main>
    <div class="modal" data-widget="modal" id="videoPlayer">
    <div class="modal__inner-wrapper">
    <a class="modal__close js-modal-close" href="#">
    <svg class="icon"><use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-close" xmlns:xlink="http://www.w3.org/1999/xlink"></use></svg>
    </a>
    <div class="fixed-cols fixed-cols--modal fixed-cols--t-dark">
    <div class="flex-grid">
    <div class="col-9 col-8-wide col-12-desk col-12-m fixed-cols__primary js-main-col">
    <div class="fixed-cols__primary-top js-single-video">
    <section class="video-player video-player--modal wrapper" data-player-name="playlistPlayer" data-widget="video-page-player">
    <div class="inline-player" data-script="ipl_video" data-widget="video-player">
    <video autoplay="true" class="inline-player__content video-js" controls="" data-account="3588749423001" data-embed="default" data-player="H1Xzd8U6g" data-tracker-action="VIEW" data-tracker-id="" data-tracker-type="VIDEO" data-video-id="" id="playlistPlayer"></video>
    </div>
    <div class="video-player__details col-12">
    <h1 class="video-player__title js-player-title"></h1>
    <p class="video-player__description js-player-description"></p>
    <ul class="inline-list">
    <li>
    <svg class="icon video-player__watch-icn">
    <use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-eye" xmlns:xlink="http://www.w3.org/1999/xlink"></use>
    </svg>
    <strong class="js-main-player-views"></strong>
    </li>
    <li class="video-player__date js-player-date"></li>
    </ul>
    </div>
    <div class="video-player__share col-10 col-12-tab js-video-share">
    </div>
    </section>
    </div>
    <div class="fixed-cols__primary-bottom js-additional-content u-hide-desktop">
    <section class="widget" data-content-type="video" data-link-to="/video/magic-moments" data-tags="ipl-magic,indian-premier-league" data-title="Magic Moments" data-widget="content-list-loader"></section>
    <section class="widget" data-content-type="video" data-link-to="/video/all" data-tags="indian-premier-league" data-title="Latest Videos" data-widget="content-list-loader"></section>
    </div>
    </div>
    <div class="col-3 col-4-wide col-12-desk fixed-cols__secondary js-video-sidebar js-sidebar-desktop">
    </div>
    </div>
    </div>
    </div>
    </div>
    <footer class="page-footer" role="contentinfo">
    <div class="promo-list">
    <div class="wrapper">
    <ul class="promo-list__items">
    <li class="promo-list__item">
    <span class="promo-list__title">Title Sponsor</span>
    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">
    <a class="promo-list__sponsor" href="https://www.vivo.com/in/" target="_self">
    <div class="js-lazy-load u-observable" data-alt="VIVO - Title Sponsor" data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2021/02/09/a67d89ee-5a3b-44ff-b1c3-3f8c50f4cd20/Vivo-Sample-3.png?height=60&amp;width=168" data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2021/02/09/a67d89ee-5a3b-44ff-b1c3-3f8c50f4cd20/Vivo-Sample-3.png?height=120&amp;width=336" data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2021/02/09/a67d89ee-5a3b-44ff-b1c3-3f8c50f4cd20/Vivo-Sample-3.png?height=60&amp;width=168" data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2021/02/09/a67d89ee-5a3b-44ff-b1c3-3f8c50f4cd20/Vivo-Sample-3.png?height=120&amp;width=336" data-object-fit="false" data-picture-in-view="false">
    </div>
    </a>
    </div>
    </li>
    </ul>
    </div>
    </div>
    <div class="promo-list">
    <div class="wrapper">
    <ul class="promo-list__items">
    <li class="promo-list__item">
    <span class="promo-list__title">Official Broadcaster</span>
    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">
    <a class="promo-list__sponsor" href="https://www.hotstar.com/" target="_self">
    <div class="js-lazy-load u-observable" data-alt="Star Sports - Partner" data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/d09cbee2-420c-4950-a25c-bedb0cb491bf/star-sports.png?height=80&amp;width=100" data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/d09cbee2-420c-4950-a25c-bedb0cb491bf/star-sports.png?height=160&amp;width=200" data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/d09cbee2-420c-4950-a25c-bedb0cb491bf/star-sports.png?height=80&amp;width=100" data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/d09cbee2-420c-4950-a25c-bedb0cb491bf/star-sports.png?height=160&amp;width=200" data-object-fit="false" data-picture-in-view="false">
    </div>
    </a>
    </div>
    </li>
    <li class="promo-list__item">
    <span class="promo-list__title">Official Digital Streaming Partner</span>
    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">
    <a class="promo-list__sponsor" href="https://www.hotstar.com/" rel="nofollow" target="_blank">
    <div class="js-lazy-load u-observable" data-alt="Disney+ Hotstar - Sponsor" data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/15265897-583c-4216-b643-9705df72b6fe/sponsor-hotstar.png?height=80&amp;width=100" data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/15265897-583c-4216-b643-9705df72b6fe/sponsor-hotstar.png?height=160&amp;width=200" data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/15265897-583c-4216-b643-9705df72b6fe/sponsor-hotstar.png?height=80&amp;width=100" data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/15265897-583c-4216-b643-9705df72b6fe/sponsor-hotstar.png?height=160&amp;width=200" data-object-fit="false" data-picture-in-view="false">
    </div>
    </a>
    </div>
    </li>
    <li class="promo-list__item promo-list__item--multiple">
    <span class="promo-list__title">Official Partners</span>
    <ul class="inline-list promo-list__sub-list">
    <li>
    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">
    <a class="promo-list__sponsor" href="https://cars.tatamotors.com/suv/safari" target="_self">
    <div class="js-lazy-load u-observable" data-alt="Safari - Official Partner" data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2021/02/12/1ef4ebc7-e65b-4ede-a11d-05bb46928578/safari-logo-png.png?height=36&amp;width=136" data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2021/02/12/1ef4ebc7-e65b-4ede-a11d-05bb46928578/safari-logo-png.png?height=72&amp;width=272" data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2021/02/12/1ef4ebc7-e65b-4ede-a11d-05bb46928578/safari-logo-png.png?height=36&amp;width=136" data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2021/02/12/1ef4ebc7-e65b-4ede-a11d-05bb46928578/safari-logo-png.png?height=72&amp;width=272" data-object-fit="false" data-picture-in-view="false">
    </div>
    </a>
    </div>
    </li>
    <li class="">
    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">
    <a class="promo-list__sponsor" href="https://www.dream11.com/" target="_self">
    <div class="js-lazy-load u-observable" data-alt="Dream11 - Official Partner" data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2021/02/12/dedd475c-fc82-47d6-a992-1f5e5c2d0b1e/dream-11-final-logo.png?height=34&amp;width=128.5" data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2021/02/12/dedd475c-fc82-47d6-a992-1f5e5c2d0b1e/dream-11-final-logo.png?height=68&amp;width=257" data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2021/02/12/dedd475c-fc82-47d6-a992-1f5e5c2d0b1e/dream-11-final-logo.png?height=34&amp;width=128.5" data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2021/02/12/dedd475c-fc82-47d6-a992-1f5e5c2d0b1e/dream-11-final-logo.png?height=68&amp;width=257" data-object-fit="false" data-picture-in-view="false">
    </div>
    </a>
    </div>
    </li>
    <li class="">
    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">
    <a class="promo-list__sponsor" href="https://unacademy.com/" rel="nofollow" target="_blank">
    <div class="js-lazy-load u-observable" data-alt="Official Partner - Unacademy" data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/a11c9b5b-41b1-4617-ab37-a89d97e1fc2e/sponsor-unacademy.png?height=19&amp;width=120" data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/a11c9b5b-41b1-4617-ab37-a89d97e1fc2e/sponsor-unacademy.png?height=38&amp;width=240" data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/a11c9b5b-41b1-4617-ab37-a89d97e1fc2e/sponsor-unacademy.png?height=19&amp;width=120" data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/a11c9b5b-41b1-4617-ab37-a89d97e1fc2e/sponsor-unacademy.png?height=38&amp;width=240" data-object-fit="false" data-picture-in-view="false">
    </div>
    </a>
    </div>
    </li>
    <li>
    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">
    <a class="promo-list__sponsor" href="https://www.cred.club/" rel="nofollow" target="_blank">
    <div class="js-lazy-load u-observable" data-alt="Cred - Official Partners" data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2020/09/14/171bb205-b523-42a0-9f3c-eff541cdf35f/cred-new-2.png?height=38&amp;width=85.5" data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/14/171bb205-b523-42a0-9f3c-eff541cdf35f/cred-new-2.png?height=76&amp;width=171" data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2020/09/14/171bb205-b523-42a0-9f3c-eff541cdf35f/cred-new-2.png?height=38&amp;width=85.5" data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/14/171bb205-b523-42a0-9f3c-eff541cdf35f/cred-new-2.png?height=76&amp;width=171" data-object-fit="false" data-picture-in-view="false">
    </div>
    </a>
    </div>
    </li>
    </ul>
    </li>
    <li class="promo-list__item">
    <span class="promo-list__title">Umpire Partner</span>
    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">
    <a class="promo-list__sponsor" href="https://paytm.com/" target="_self">
    <div class="js-lazy-load u-observable" data-alt="Paytm - Partner" data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/b1771f68-719a-4b2d-9db4-944f3b47b66e/sponsor-paytm.png?height=25&amp;width=81" data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/b1771f68-719a-4b2d-9db4-944f3b47b66e/sponsor-paytm.png?height=50&amp;width=162" data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/b1771f68-719a-4b2d-9db4-944f3b47b66e/sponsor-paytm.png?height=25&amp;width=81" data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/b1771f68-719a-4b2d-9db4-944f3b47b66e/sponsor-paytm.png?height=50&amp;width=162" data-object-fit="false" data-picture-in-view="false">
    </div>
    </a>
    </div>
    </li>
    <li class="promo-list__item">
    <span class="promo-list__title">Official Strategic Timeout Partner</span>
    <div class="promo-list__sponsor-wrapper" data-widget="lazy-load-images">
    <a class="promo-list__sponsor" href="https://www.ceat.com/" rel="nofollow" target="_blank">
    <div class="js-lazy-load u-observable" data-alt="CEAT - Sponsor" data-desktop-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/57a112b9-cc79-4375-8033-b5234db3ae51/sponsor-ceat.png?height=22&amp;width=74" data-desktop-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/57a112b9-cc79-4375-8033-b5234db3ae51/sponsor-ceat.png?height=44&amp;width=148" data-mobile-img="https://resources.platform.iplt20.com/photo-resources/2020/09/10/57a112b9-cc79-4375-8033-b5234db3ae51/sponsor-ceat.png?height=22&amp;width=74" data-mobile-img-retina="https://resources.platform.iplt20.com/photo-resources/2020/09/10/57a112b9-cc79-4375-8033-b5234db3ae51/sponsor-ceat.png?height=44&amp;width=148" data-object-fit="false" data-picture-in-view="false">
    </div>
    </a>
    </div>
    </li>
    </ul>
    </div>
    </div>
    <div class="page-footer__nav-section">
    <div class="page-footer__background">
    <img aria-hidden="true" class="branding-asset page-footer__background-image" src="/resources/v4.19.2/i/element-bgs/ipl_svg_background_2020-t-generic.svg"/>
    <div class="social-follow social-follow--footer">
    <h5 class="social-follow__title u-hide-phablet">FOLLOW #IPL</h5>
    <ul class="social-follow__list">
    <li class="social-follow__item">
    <a class="social-follow__link social-follow__link--facebook js-facebook-link" href="https://www.facebook.com/IPL/" rel="nofollow" target="_blank">
    <svg class="icon"><use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-facebook" xmlns:xlink="http://www.w3.org/1999/xlink"></use></svg>
    <span class="u-screen-reader">Follow IPL on Facebook</span>
    </a>
    </li>
    <li class="social-follow__item">
    <a class="social-follow__link social-follow__link--instagram js-instagram-link" href="https://www.instagram.com/iplt20/?hl=en" rel="nofollow" target="_blank">
    <svg class="icon"><use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-instagram" xmlns:xlink="http://www.w3.org/1999/xlink"></use></svg>
    <span class="u-screen-reader">Follow IPL on Instagram</span>
    </a>
    </li>
    <li class="social-follow__item">
    <a class="social-follow__link social-follow__link--twitter js-twitter-link" href="https://twitter.com/IPL" rel="nofollow" target="_blank">
    <svg class="icon"><use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-twitter" xmlns:xlink="http://www.w3.org/1999/xlink"></use></svg>
    <span class="u-screen-reader">Follow IPL on Twitter</span>
    </a>
    </li>
    </ul>
    </div>
    <div class="col-12">
    <nav class="page-footer__menu">
    <ul class="large-block-grid-5 small-block-grid-1">
    <li>
    <h5 class="footer-list__title">Quicklinks</h5>
    <ul class="footer-list large-block-grid-1 medium-block-grid-3 small-block-grid-2">
    <li><a href="/news">News</a></li>
    <li><a href="/video">Videos</a></li>
    <li><a href="/venues">Venues</a></li>
    <li><a href="/stats">Stats</a></li>
    <li><a href="/archive">Archive</a></li>
    </ul>
    </li>
    <li>
    <h5 class="footer-list__title">Teams</h5>
    <ul class="footer-list large-block-grid-1 medium-block-grid-3 small-block-grid-2">
    <li><a href="/teams/chennai-super-kings">Chennai Super Kings</a></li>
    <li><a href="/teams/delhi-capitals">Delhi Capitals</a></li>
    <li><a href="/teams/kings-xi-punjab">Kings XI Punjab</a></li>
    <li><a href="/teams/kolkata-knight-riders">Kolkata Knight Riders</a></li>
    <li><a href="/teams/mumbai-indians">Mumbai Indians</a></li>
    <li><a href="/teams/rajasthan-royals">Rajasthan Royals</a></li>
    <li><a href="/teams/royal-challengers-bangalore">Royal Challengers Bangalore</a></li>
    <li><a href="/teams/sunrisers-hyderabad">Sunrisers Hyderabad</a></li>
    </ul>
    </li>
    <li>
    <h5 class="footer-list__title">About</h5>
    <ul class="footer-list large-block-grid-1 medium-block-grid-3 small-block-grid-2">
    <li><a href="/about/about-us">About Us</a></li>
    <li><a href="/about/anti-corruption-policy">Anti Corruption Policy</a></li>
    <li><a href="/about/anti-doping-policy">Anti Doping Policy</a></li>
    <li><a href="https://iplplatform-static-files.s3.amazonaws.com/IPL/document/2020/01/23/6beaa665-8850-4ad0-8d64-baa0967a818f/TUE-Form.pdf">TUE Application Form</a></li>
    <li><a href="/about/anti-racism-policy">Anti-Discrimination Policy</a></li>
    <li><a href="/about/clothing-and-equipment-regulations">Clothing and Equipment Regulations</a></li>
    <li><a href="/about/code-of-conduct-for-players-and-team-officials">Code of Conduct for Players and Team Officials</a></li>
    </ul>
    </li>
    <li>
    <h5 class="footer-list__title">Title</h5>
    <ul class="footer-list large-block-grid-1 medium-block-grid-3 small-block-grid-2">
    <li><a href="/about/code-of-conduct-for-umpires">IPL Code of Conduct for Match officials</a></li>
    <li><a href="https://resources.platform.iplt20.com/IPL/document/2020/09/13/e81ad3af-a65c-4b95-a0d6-cd7840acf20f/IPL-2020-Brand-and-Content-Protection-Guidelines.pdf">Brand and Protection Guidelines</a></li>
    <li><a href="/about/governing-council">Governing Council</a></li>
    <li><a href="/about/match-playing-conditions">Match Playing Conditions</a></li>
    <li><a href="/about/pmoa-minimum-standard">PMOA Minimum Standard</a></li>
    <li><a href="/about/suspect-action-policy">Suspect Action Policy</a></li>
    </ul>
    </li>
    <li>
    <h5 class="footer-list__title">Contact</h5>
    <ul class="footer-list large-block-grid-1 medium-block-grid-3 small-block-grid-2">
    <li><a href="/about/contact-us">Contact Us</a></li>
    <li><a href="/about/contact-us">Sponsorship</a></li>
    </ul>
    </li>
    </ul>
    </nav>
    </div>
    </div>
    </div>
    <div class="page-footer__bottom">
    <div class="page-footer__bottom-content">
    <span class="ipl-copy">© Copyright IPL, BCCI 2021. All Rights Reserved.</span>
    <ul class="foot-menu inline-list">
    <li><a href="/about/privacy-policy">Privacy Policy</a></li>
    </ul>
    </div>
    </div>
    </footer>
    <section class="match-scroller-container">
    <div class="match-scroller__fixed-container">
    <section class="match-scroller" data-script="ipl_match-scroller" data-widget="match-scroller">
    <nav class="match-scroller__nav js-match-scroller-nav">
    <button aria-label="Previous" class="match-scroller__btn match-scroller__btn--prev js-match-scroller-prev">
    <svg class="icon"><use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-left" xmlns:xlink="http://www.w3.org/1999/xlink"></use></svg>
    </button>
    <button aria-label="Next" class="match-scroller__btn match-scroller__btn--next js-match-scroller-next">
    <svg class="icon"><use xlink:href="/resources/v4.19.2/i/svg-output/icons.svg#icn-chevron-right" xmlns:xlink="http://www.w3.org/1999/xlink"></use></svg>
    </button>
    </nav>
    <ul class="match-scroller__list js-match-scroller-list scroller-toggle slider-fixtures">
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Sep</span>
    <span class="match-scroller__day">19</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22236" data-match-state="C" data-timestamp="1600524000000" data-tournament-id="18790" href="/match/2020/01">
    <p class="match-item__summary">Chennai Super Kings won by 5 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-MI">
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    <div class="match-item__team-logo tLogo70x MI"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        162
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            9
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        166
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-CSK">
    <div class="match-item__team-logo tLogo70x CSK"></div>
    <p class="match-item__team-name" title="Chennai Super Kings">
                        CSK
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Sep</span>
    <span class="match-scroller__day">20</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22237" data-match-state="C" data-timestamp="1600610400000" data-tournament-id="18790" href="/match/2020/02">
    <p class="match-item__summary">Match tied (Delhi Capitals won the Super Over)</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-DC">
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    <div class="match-item__team-logo tLogo70x DC"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        157
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            8
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        157
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            8
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-PBKS">
    <div class="match-item__team-logo tLogo70x PBKS"></div>
    <p class="match-item__team-name" title="Punjab Kings">
                        PBKS
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Sep</span>
    <span class="match-scroller__day">21</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22238" data-match-state="C" data-timestamp="1600696800000" data-tournament-id="18790" href="/match/2020/03">
    <p class="match-item__summary">Royal Challengers Bangalore won by 10 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-SRH">
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    <div class="match-item__team-logo tLogo70x SRH"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        153
                    </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        163
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RCB">
    <div class="match-item__team-logo tLogo70x RCB"></div>
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Sep</span>
    <span class="match-scroller__day">22</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22239" data-match-state="C" data-timestamp="1600783200000" data-tournament-id="18790" href="/match/2020/04">
    <p class="match-item__summary">Rajasthan Royals won by 16 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-RR">
    <p class="match-item__team-name" title="Rajasthan Royals">
                        RR
                    </p>
    <div class="match-item__team-logo tLogo70x RR"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        216
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            7
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        200
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-CSK">
    <div class="match-item__team-logo tLogo70x CSK"></div>
    <p class="match-item__team-name" title="Chennai Super Kings">
                        CSK
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Sep</span>
    <span class="match-scroller__day">23</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22240" data-match-state="C" data-timestamp="1600869600000" data-tournament-id="18790" href="/match/2020/05">
    <p class="match-item__summary">Mumbai Indians won by 49 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-KKR">
    <p class="match-item__team-name" title="Kolkata Knight Riders">
                        KKR
                    </p>
    <div class="match-item__team-logo tLogo70x KKR"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        146
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            9
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        195
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-MI">
    <div class="match-item__team-logo tLogo70x MI"></div>
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Sep</span>
    <span class="match-scroller__day">24</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22241" data-match-state="C" data-timestamp="1600956000000" data-tournament-id="18790" href="/match/2020/06">
    <p class="match-item__summary">Punjab Kings won by 97 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-PBKS">
    <p class="match-item__team-name" title="Punjab Kings">
                        PBKS
                    </p>
    <div class="match-item__team-logo tLogo70x PBKS"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        206
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            3
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        109
                    </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RCB">
    <div class="match-item__team-logo tLogo70x RCB"></div>
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Sep</span>
    <span class="match-scroller__day">25</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22242" data-match-state="C" data-timestamp="1601042400000" data-tournament-id="18790" href="/match/2020/07">
    <p class="match-item__summary">Delhi Capitals won by 44 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-CSK">
    <p class="match-item__team-name" title="Chennai Super Kings">
                        CSK
                    </p>
    <div class="match-item__team-logo tLogo70x CSK"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        131
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            7
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        175
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            3
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-DC">
    <div class="match-item__team-logo tLogo70x DC"></div>
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Sep</span>
    <span class="match-scroller__day">26</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22243" data-match-state="C" data-timestamp="1601128800000" data-tournament-id="18790" href="/match/2020/08">
    <p class="match-item__summary">Kolkata Knight Riders won by 7 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-KKR">
    <p class="match-item__team-name" title="Kolkata Knight Riders">
                        KKR
                    </p>
    <div class="match-item__team-logo tLogo70x KKR"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        145
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            3
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        142
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-SRH">
    <div class="match-item__team-logo tLogo70x SRH"></div>
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Sep</span>
    <span class="match-scroller__day">27</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22244" data-match-state="C" data-timestamp="1601215200000" data-tournament-id="18790" href="/match/2020/09">
    <p class="match-item__summary">Rajasthan Royals won by 4 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-RR">
    <p class="match-item__team-name" title="Rajasthan Royals">
                        RR
                    </p>
    <div class="match-item__team-logo tLogo70x RR"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        226
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        223
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            2
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-PBKS">
    <div class="match-item__team-logo tLogo70x PBKS"></div>
    <p class="match-item__team-name" title="Punjab Kings">
                        PBKS
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Sep</span>
    <span class="match-scroller__day">28</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22245" data-match-state="C" data-timestamp="1601301600000" data-tournament-id="18790" href="/match/2020/10">
    <p class="match-item__summary">Match tied (Royal Challengers Bangalore won the Super Over)</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-RCB">
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    <div class="match-item__team-logo tLogo70x RCB"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        201
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            3
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        201
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-MI">
    <div class="match-item__team-logo tLogo70x MI"></div>
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Sep</span>
    <span class="match-scroller__day">29</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22246" data-match-state="C" data-timestamp="1601388000000" data-tournament-id="18790" href="/match/2020/11">
    <p class="match-item__summary">Sunrisers Hyderabad won by 15 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-DC">
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    <div class="match-item__team-logo tLogo70x DC"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        147
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            7
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        162
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-SRH">
    <div class="match-item__team-logo tLogo70x SRH"></div>
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Sep</span>
    <span class="match-scroller__day">30</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22247" data-match-state="C" data-timestamp="1601474400000" data-tournament-id="18790" href="/match/2020/12">
    <p class="match-item__summary">Kolkata Knight Riders won by 37 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-RR">
    <p class="match-item__team-name" title="Rajasthan Royals">
                        RR
                    </p>
    <div class="match-item__team-logo tLogo70x RR"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        137
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            9
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        174
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-KKR">
    <div class="match-item__team-logo tLogo70x KKR"></div>
    <p class="match-item__team-name" title="Kolkata Knight Riders">
                        KKR
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">1</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22248" data-match-state="C" data-timestamp="1601560800000" data-tournament-id="18790" href="/match/2020/13">
    <p class="match-item__summary">Mumbai Indians won by 48 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-PBKS">
    <p class="match-item__team-name" title="Punjab Kings">
                        PBKS
                    </p>
    <div class="match-item__team-logo tLogo70x PBKS"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        143
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            8
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        191
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-MI">
    <div class="match-item__team-logo tLogo70x MI"></div>
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">2</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22249" data-match-state="C" data-timestamp="1601647200000" data-tournament-id="18790" href="/match/2020/14">
    <p class="match-item__summary">Sunrisers Hyderabad won by 7 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-CSK">
    <p class="match-item__team-name" title="Chennai Super Kings">
                        CSK
                    </p>
    <div class="match-item__team-logo tLogo70x CSK"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        157
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        164
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-SRH">
    <div class="match-item__team-logo tLogo70x SRH"></div>
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">3</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22250" data-match-state="C" data-timestamp="1601719200000" data-tournament-id="18790" href="/match/2020/15">
    <p class="match-item__summary">Royal Challengers Bangalore won by 8 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-RCB">
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    <div class="match-item__team-logo tLogo70x RCB"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        158
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            2
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        154
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RR">
    <div class="match-item__team-logo tLogo70x RR"></div>
    <p class="match-item__team-name" title="Rajasthan Royals">
                        RR
                    </p>
    </div>
    </div>
    </a>
    </li>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22251" data-match-state="C" data-timestamp="1601733600000" data-tournament-id="18790" href="/match/2020/16">
    <p class="match-item__summary">Delhi Capitals won by 18 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-DC">
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    <div class="match-item__team-logo tLogo70x DC"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        228
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        210
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            8
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-KKR">
    <div class="match-item__team-logo tLogo70x KKR"></div>
    <p class="match-item__team-name" title="Kolkata Knight Riders">
                        KKR
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">4</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22252" data-match-state="C" data-timestamp="1601805600000" data-tournament-id="18790" href="/match/2020/17">
    <p class="match-item__summary">Mumbai Indians won by 34 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-MI">
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    <div class="match-item__team-logo tLogo70x MI"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        208
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        174
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            7
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-SRH">
    <div class="match-item__team-logo tLogo70x SRH"></div>
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    </div>
    </div>
    </a>
    </li>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22253" data-match-state="C" data-timestamp="1601820000000" data-tournament-id="18790" href="/match/2020/18">
    <p class="match-item__summary">Chennai Super Kings won by 10 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-PBKS">
    <p class="match-item__team-name" title="Punjab Kings">
                        PBKS
                    </p>
    <div class="match-item__team-logo tLogo70x PBKS"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        178
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        181
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            0
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-CSK">
    <div class="match-item__team-logo tLogo70x CSK"></div>
    <p class="match-item__team-name" title="Chennai Super Kings">
                        CSK
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">5</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22254" data-match-state="C" data-timestamp="1601906400000" data-tournament-id="18790" href="/match/2020/19">
    <p class="match-item__summary">Delhi Capitals won by 59 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-RCB">
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    <div class="match-item__team-logo tLogo70x RCB"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        137
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            9
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        196
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-DC">
    <div class="match-item__team-logo tLogo70x DC"></div>
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">6</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22255" data-match-state="C" data-timestamp="1601992800000" data-tournament-id="18790" href="/match/2020/20">
    <p class="match-item__summary">Mumbai Indians won by 57 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-MI">
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    <div class="match-item__team-logo tLogo70x MI"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        193
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        136
                    </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RR">
    <div class="match-item__team-logo tLogo70x RR"></div>
    <p class="match-item__team-name" title="Rajasthan Royals">
                        RR
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">7</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22256" data-match-state="C" data-timestamp="1602079200000" data-tournament-id="18790" href="/match/2020/21">
    <p class="match-item__summary">Kolkata Knight Riders won by 10 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-KKR">
    <p class="match-item__team-name" title="Kolkata Knight Riders">
                        KKR
                    </p>
    <div class="match-item__team-logo tLogo70x KKR"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        167
                    </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        157
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-CSK">
    <div class="match-item__team-logo tLogo70x CSK"></div>
    <p class="match-item__team-name" title="Chennai Super Kings">
                        CSK
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">8</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22257" data-match-state="C" data-timestamp="1602165600000" data-tournament-id="18790" href="/match/2020/22">
    <p class="match-item__summary">Sunrisers Hyderabad won by 69 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-SRH">
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    <div class="match-item__team-logo tLogo70x SRH"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        201
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        132
                    </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-PBKS">
    <div class="match-item__team-logo tLogo70x PBKS"></div>
    <p class="match-item__team-name" title="Punjab Kings">
                        PBKS
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">9</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22258" data-match-state="C" data-timestamp="1602252000000" data-tournament-id="18790" href="/match/2020/23">
    <p class="match-item__summary">Delhi Capitals won by 46 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-RR">
    <p class="match-item__team-name" title="Rajasthan Royals">
                        RR
                    </p>
    <div class="match-item__team-logo tLogo70x RR"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        138
                    </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        184
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            8
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-DC">
    <div class="match-item__team-logo tLogo70x DC"></div>
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">10</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22259" data-match-state="C" data-timestamp="1602324000000" data-tournament-id="18790" href="/match/2020/24">
    <p class="match-item__summary">Kolkata Knight Riders won by 2 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-PBKS">
    <p class="match-item__team-name" title="Punjab Kings">
                        PBKS
                    </p>
    <div class="match-item__team-logo tLogo70x PBKS"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        162
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        164
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-KKR">
    <div class="match-item__team-logo tLogo70x KKR"></div>
    <p class="match-item__team-name" title="Kolkata Knight Riders">
                        KKR
                    </p>
    </div>
    </div>
    </a>
    </li>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22260" data-match-state="C" data-timestamp="1602338400000" data-tournament-id="18790" href="/match/2020/25">
    <p class="match-item__summary">Royal Challengers Bangalore won by 37 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-CSK">
    <p class="match-item__team-name" title="Chennai Super Kings">
                        CSK
                    </p>
    <div class="match-item__team-logo tLogo70x CSK"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        132
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            8
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        169
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RCB">
    <div class="match-item__team-logo tLogo70x RCB"></div>
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">11</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22261" data-match-state="C" data-timestamp="1602410400000" data-tournament-id="18790" href="/match/2020/26">
    <p class="match-item__summary">Rajasthan Royals won by 5 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-SRH">
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    <div class="match-item__team-logo tLogo70x SRH"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        158
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        163
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RR">
    <div class="match-item__team-logo tLogo70x RR"></div>
    <p class="match-item__team-name" title="Rajasthan Royals">
                        RR
                    </p>
    </div>
    </div>
    </a>
    </li>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22262" data-match-state="C" data-timestamp="1602424800000" data-tournament-id="18790" href="/match/2020/27">
    <p class="match-item__summary">Mumbai Indians won by 5 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-MI">
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    <div class="match-item__team-logo tLogo70x MI"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        166
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        162
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-DC">
    <div class="match-item__team-logo tLogo70x DC"></div>
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">12</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22263" data-match-state="C" data-timestamp="1602511200000" data-tournament-id="18790" href="/match/2020/28">
    <p class="match-item__summary">Royal Challengers Bangalore won by 82 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-RCB">
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    <div class="match-item__team-logo tLogo70x RCB"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        194
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            2
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        112
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            9
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-KKR">
    <div class="match-item__team-logo tLogo70x KKR"></div>
    <p class="match-item__team-name" title="Kolkata Knight Riders">
                        KKR
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">13</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22264" data-match-state="C" data-timestamp="1602597600000" data-tournament-id="18790" href="/match/2020/29">
    <p class="match-item__summary">Chennai Super Kings won by 20 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-SRH">
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    <div class="match-item__team-logo tLogo70x SRH"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        147
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            8
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        167
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-CSK">
    <div class="match-item__team-logo tLogo70x CSK"></div>
    <p class="match-item__team-name" title="Chennai Super Kings">
                        CSK
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">14</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22265" data-match-state="C" data-timestamp="1602684000000" data-tournament-id="18790" href="/match/2020/30">
    <p class="match-item__summary">Delhi Capitals won by 13 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-DC">
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    <div class="match-item__team-logo tLogo70x DC"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        161
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            7
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        148
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            8
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RR">
    <div class="match-item__team-logo tLogo70x RR"></div>
    <p class="match-item__team-name" title="Rajasthan Royals">
                        RR
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">15</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22266" data-match-state="C" data-timestamp="1602770400000" data-tournament-id="18790" href="/match/2020/31">
    <p class="match-item__summary">Punjab Kings won by 8 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-RCB">
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    <div class="match-item__team-logo tLogo70x RCB"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        171
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        177
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            2
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-PBKS">
    <div class="match-item__team-logo tLogo70x PBKS"></div>
    <p class="match-item__team-name" title="Punjab Kings">
                        PBKS
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">16</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22267" data-match-state="C" data-timestamp="1602856800000" data-tournament-id="18790" href="/match/2020/32">
    <p class="match-item__summary">Mumbai Indians won by 8 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-MI">
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    <div class="match-item__team-logo tLogo70x MI"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        149
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            2
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        148
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-KKR">
    <div class="match-item__team-logo tLogo70x KKR"></div>
    <p class="match-item__team-name" title="Kolkata Knight Riders">
                        KKR
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">17</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22268" data-match-state="C" data-timestamp="1602928800000" data-tournament-id="18790" href="/match/2020/33">
    <p class="match-item__summary">Royal Challengers Bangalore won by 7 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-RR">
    <p class="match-item__team-name" title="Rajasthan Royals">
                        RR
                    </p>
    <div class="match-item__team-logo tLogo70x RR"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        177
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        179
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            3
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RCB">
    <div class="match-item__team-logo tLogo70x RCB"></div>
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    </div>
    </div>
    </a>
    </li>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22269" data-match-state="C" data-timestamp="1602943200000" data-tournament-id="18790" href="/match/2020/34">
    <p class="match-item__summary">Delhi Capitals won by 5 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-DC">
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    <div class="match-item__team-logo tLogo70x DC"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        185
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        179
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-CSK">
    <div class="match-item__team-logo tLogo70x CSK"></div>
    <p class="match-item__team-name" title="Chennai Super Kings">
                        CSK
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">18</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22270" data-match-state="C" data-timestamp="1603015200000" data-tournament-id="18790" href="/match/2020/35">
    <p class="match-item__summary">Match tied (Kolkata Knight Riders won the Super Over)</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-SRH">
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    <div class="match-item__team-logo tLogo70x SRH"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        163
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        163
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-KKR">
    <div class="match-item__team-logo tLogo70x KKR"></div>
    <p class="match-item__team-name" title="Kolkata Knight Riders">
                        KKR
                    </p>
    </div>
    </div>
    </a>
    </li>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22271" data-match-state="C" data-timestamp="1603029600000" data-tournament-id="18790" href="/match/2020/36">
    <p class="match-item__summary">Match tied (Kings XI Punjab won on second Super Over)</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-MI">
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    <div class="match-item__team-logo tLogo70x MI"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        176
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        176
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-PBKS">
    <div class="match-item__team-logo tLogo70x PBKS"></div>
    <p class="match-item__team-name" title="Punjab Kings">
                        PBKS
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">19</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22272" data-match-state="C" data-timestamp="1603116000000" data-tournament-id="18790" href="/match/2020/37">
    <p class="match-item__summary">Rajasthan Royals won by 7 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-CSK">
    <p class="match-item__team-name" title="Chennai Super Kings">
                        CSK
                    </p>
    <div class="match-item__team-logo tLogo70x CSK"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        125
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        126
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            3
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RR">
    <div class="match-item__team-logo tLogo70x RR"></div>
    <p class="match-item__team-name" title="Rajasthan Royals">
                        RR
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">20</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22273" data-match-state="C" data-timestamp="1603202400000" data-tournament-id="18790" href="/match/2020/38">
    <p class="match-item__summary">Punjab Kings won by 5 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-PBKS">
    <p class="match-item__team-name" title="Punjab Kings">
                        PBKS
                    </p>
    <div class="match-item__team-logo tLogo70x PBKS"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        167
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        164
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-DC">
    <div class="match-item__team-logo tLogo70x DC"></div>
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">21</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22274" data-match-state="C" data-timestamp="1603288800000" data-tournament-id="18790" href="/match/2020/39">
    <p class="match-item__summary">Royal Challengers Bangalore won by 8 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-KKR">
    <p class="match-item__team-name" title="Kolkata Knight Riders">
                        KKR
                    </p>
    <div class="match-item__team-logo tLogo70x KKR"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        84
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            8
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        85
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            2
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RCB">
    <div class="match-item__team-logo tLogo70x RCB"></div>
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">22</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22275" data-match-state="C" data-timestamp="1603375200000" data-tournament-id="18790" href="/match/2020/40">
    <p class="match-item__summary">Sunrisers Hyderabad won by 8 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-RR">
    <p class="match-item__team-name" title="Rajasthan Royals">
                        RR
                    </p>
    <div class="match-item__team-logo tLogo70x RR"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        154
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        156
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            2
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-SRH">
    <div class="match-item__team-logo tLogo70x SRH"></div>
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">23</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22276" data-match-state="C" data-timestamp="1603461600000" data-tournament-id="18790" href="/match/2020/41">
    <p class="match-item__summary">Mumbai Indians won by 10 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-CSK">
    <p class="match-item__team-name" title="Chennai Super Kings">
                        CSK
                    </p>
    <div class="match-item__team-logo tLogo70x CSK"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        114
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            9
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        116
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            0
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-MI">
    <div class="match-item__team-logo tLogo70x MI"></div>
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">24</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22277" data-match-state="C" data-timestamp="1603533600000" data-tournament-id="18790" href="/match/2020/42">
    <p class="match-item__summary">Kolkata Knight Riders won by 59 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-KKR">
    <p class="match-item__team-name" title="Kolkata Knight Riders">
                        KKR
                    </p>
    <div class="match-item__team-logo tLogo70x KKR"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        194
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        135
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            9
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-DC">
    <div class="match-item__team-logo tLogo70x DC"></div>
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    </div>
    </div>
    </a>
    </li>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22278" data-match-state="C" data-timestamp="1603548000000" data-tournament-id="18790" href="/match/2020/43">
    <p class="match-item__summary">Punjab Kings won by 12 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-PBKS">
    <p class="match-item__team-name" title="Punjab Kings">
                        PBKS
                    </p>
    <div class="match-item__team-logo tLogo70x PBKS"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        126
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            7
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        114
                    </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-SRH">
    <div class="match-item__team-logo tLogo70x SRH"></div>
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">25</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22279" data-match-state="C" data-timestamp="1603620000000" data-tournament-id="18790" href="/match/2020/44">
    <p class="match-item__summary">Chennai Super Kings won by 8 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-RCB">
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    <div class="match-item__team-logo tLogo70x RCB"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        145
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        150
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            2
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-CSK">
    <div class="match-item__team-logo tLogo70x CSK"></div>
    <p class="match-item__team-name" title="Chennai Super Kings">
                        CSK
                    </p>
    </div>
    </div>
    </a>
    </li>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22280" data-match-state="C" data-timestamp="1603634400000" data-tournament-id="18790" href="/match/2020/45">
    <p class="match-item__summary">Rajasthan Royals won by 8 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-RR">
    <p class="match-item__team-name" title="Rajasthan Royals">
                        RR
                    </p>
    <div class="match-item__team-logo tLogo70x RR"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        196
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            2
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        195
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-MI">
    <div class="match-item__team-logo tLogo70x MI"></div>
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">26</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22281" data-match-state="C" data-timestamp="1603720800000" data-tournament-id="18790" href="/match/2020/46">
    <p class="match-item__summary">Punjab Kings won by 8 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-KKR">
    <p class="match-item__team-name" title="Kolkata Knight Riders">
                        KKR
                    </p>
    <div class="match-item__team-logo tLogo70x KKR"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        149
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            9
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        150
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            2
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-PBKS">
    <div class="match-item__team-logo tLogo70x PBKS"></div>
    <p class="match-item__team-name" title="Punjab Kings">
                        PBKS
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">27</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22282" data-match-state="C" data-timestamp="1603807200000" data-tournament-id="18790" href="/match/2020/47">
    <p class="match-item__summary">Sunrisers Hyderabad won by 88 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-SRH">
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    <div class="match-item__team-logo tLogo70x SRH"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        219
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            2
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        131
                    </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-DC">
    <div class="match-item__team-logo tLogo70x DC"></div>
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">28</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22283" data-match-state="C" data-timestamp="1603893600000" data-tournament-id="18790" href="/match/2020/48">
    <p class="match-item__summary">Mumbai Indians won by 5 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-MI">
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    <div class="match-item__team-logo tLogo70x MI"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        166
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        164
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RCB">
    <div class="match-item__team-logo tLogo70x RCB"></div>
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">29</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22284" data-match-state="C" data-timestamp="1603980000000" data-tournament-id="18790" href="/match/2020/49">
    <p class="match-item__summary">Chennai Super Kings won by 6 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-CSK">
    <p class="match-item__team-name" title="Chennai Super Kings">
                        CSK
                    </p>
    <div class="match-item__team-logo tLogo70x CSK"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        178
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        172
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-KKR">
    <div class="match-item__team-logo tLogo70x KKR"></div>
    <p class="match-item__team-name" title="Kolkata Knight Riders">
                        KKR
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">30</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22285" data-match-state="C" data-timestamp="1604066400000" data-tournament-id="18790" href="/match/2020/50">
    <p class="match-item__summary">Rajasthan Royals won by 7 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-PBKS">
    <p class="match-item__team-name" title="Punjab Kings">
                        PBKS
                    </p>
    <div class="match-item__team-logo tLogo70x PBKS"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        185
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        186
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            3
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RR">
    <div class="match-item__team-logo tLogo70x RR"></div>
    <p class="match-item__team-name" title="Rajasthan Royals">
                        RR
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Oct</span>
    <span class="match-scroller__day">31</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22286" data-match-state="C" data-timestamp="1604138400000" data-tournament-id="18790" href="/match/2020/51">
    <p class="match-item__summary">Mumbai Indians won by 9 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-DC">
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    <div class="match-item__team-logo tLogo70x DC"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        110
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            9
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        111
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            1
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-MI">
    <div class="match-item__team-logo tLogo70x MI"></div>
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    </div>
    </div>
    </a>
    </li>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22287" data-match-state="C" data-timestamp="1604152800000" data-tournament-id="18790" href="/match/2020/52">
    <p class="match-item__summary">Sunrisers Hyderabad won by 5 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-RCB">
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    <div class="match-item__team-logo tLogo70x RCB"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_B_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        120
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            7
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        121
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-SRH">
    <div class="match-item__team-logo tLogo70x SRH"></div>
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Nov</span>
    <span class="match-scroller__day">1</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22288" data-match-state="C" data-timestamp="1604224800000" data-tournament-id="18790" href="/match/2020/53">
    <p class="match-item__summary">Chennai Super Kings won by 9 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-CSK">
    <p class="match-item__team-name" title="Chennai Super Kings">
                        CSK
                    </p>
    <div class="match-item__team-logo tLogo70x CSK"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        154
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            1
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        153
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            6
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-PBKS">
    <div class="match-item__team-logo tLogo70x PBKS"></div>
    <p class="match-item__team-name" title="Punjab Kings">
                        PBKS
                    </p>
    </div>
    </div>
    </a>
    </li>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22289" data-match-state="C" data-timestamp="1604239200000" data-tournament-id="18790" href="/match/2020/54">
    <p class="match-item__summary">Kolkata Knight Riders won by 60 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-KKR">
    <p class="match-item__team-name" title="Kolkata Knight Riders">
                        KKR
                    </p>
    <div class="match-item__team-logo tLogo70x KKR"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        191
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            7
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        131
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            9
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RR">
    <div class="match-item__team-logo tLogo70x RR"></div>
    <p class="match-item__team-name" title="Rajasthan Royals">
                        RR
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Nov</span>
    <span class="match-scroller__day">2</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22290" data-match-state="C" data-timestamp="1604325600000" data-tournament-id="18790" href="/match/2020/55">
    <p class="match-item__summary">Delhi Capitals won by 6 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-DC">
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    <div class="match-item__team-logo tLogo70x DC"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        154
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        152
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            7
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RCB">
    <div class="match-item__team-logo tLogo70x RCB"></div>
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Nov</span>
    <span class="match-scroller__day">3</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22291" data-match-state="C" data-timestamp="1604412000000" data-tournament-id="18790" href="/match/2020/56">
    <p class="match-item__summary">Sunrisers Hyderabad won by 10 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-SRH">
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    <div class="match-item__team-logo tLogo70x SRH"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        151
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            0
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        149
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            8
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-MI">
    <div class="match-item__team-logo tLogo70x MI"></div>
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Nov</span>
    <span class="match-scroller__day">5</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22359" data-match-state="C" data-timestamp="1604584800000" data-tournament-id="18790" href="/match/2020/57">
    <p class="match-item__summary">Mumbai Indians won by 57 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-MI">
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    <div class="match-item__team-logo tLogo70x MI"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        200
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        143
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            8
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-DC">
    <div class="match-item__team-logo tLogo70x DC"></div>
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Nov</span>
    <span class="match-scroller__day">6</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22360" data-match-state="C" data-timestamp="1604671200000" data-tournament-id="18790" href="/match/2020/58">
    <p class="match-item__summary">Sunrisers Hyderabad won by 6 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-SRH">
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    <div class="match-item__team-logo tLogo70x SRH"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        132
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            4
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        131
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            7
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-RCB">
    <div class="match-item__team-logo tLogo70x RCB"></div>
    <p class="match-item__team-name" title="Royal Challengers Bangalore">
                        RCB
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Nov</span>
    <span class="match-scroller__day">8</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22361" data-match-state="C" data-timestamp="1604844000000" data-tournament-id="18790" href="/match/2020/59">
    <p class="match-item__summary">Delhi Capitals won by 17 runs</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-DC">
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    <div class="match-item__team-logo tLogo70x DC"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        189
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            3
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        172
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            8
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-SRH">
    <div class="match-item__team-logo tLogo70x SRH"></div>
    <p class="match-item__team-name" title="Sunrisers Hyderabad">
                        SRH
                    </p>
    </div>
    </div>
    </a>
    </li>
    <h2 class="match-scroller__date">
    <span class="match-scroller__month">Nov</span>
    <span class="match-scroller__day">10</span>
    </h2>
    <li class="match-scroller__item">
    <a class="match-item js-match-item" data-match-id="22362" data-match-state="C" data-timestamp="1605016800000" data-tournament-id="18790" href="/match/2020/60">
    <p class="match-item__summary">Mumbai Indians won by 5 wickets</p>
    <div class="match-item__content">
    <div class="match-item__team match-item__team--a t-MI">
    <p class="match-item__team-name" title="Mumbai Indians">
                        MI
                    </p>
    <div class="match-item__team-logo tLogo70x MI"></div>
    </div>
    <div class="match-item__scorebox">
    <!-- TEAM_A_WON -->
    <span class="match-item__score match-item__score--a">
    <span class="match-item__score--runs">
                        157
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            5
                        </span>
    </span>
    <span class="match-item__versus">V</span>
    <span class="match-item__score match-item__score--b">
    <span class="match-item__score--runs">
                        156
                    </span>
    <span class="match-item__score--delimiter">/</span>
    <span class="match-item__score--wkts">
                            7
                        </span>
    </span>
    </div>
    <div class="match-item__team match-item__team--b t-DC">
    <div class="match-item__team-logo tLogo70x DC"></div>
    <p class="match-item__team-name" title="Delhi Capitals">
                        DC
                    </p>
    </div>
    </div>
    </a>
    </li>
    </ul>
    </section>
    </div>
    </section>
    <!-- Script includes -->
    <script src="/resources/v4.19.2/scripts/vendors.min.js"></script>
    <script src="/resources/v4.19.2/scripts/main.min.js"></script>
    <script src="/resources/v4.19.2/widgets/common.min.js"></script>
    </body>
    </html>
    


```python
my_soup.findAll('h2',{})#find all returns every element in h2
```




    [<h2 class="match-scroller__date">
     <span class="match-scroller__month">Sep</span>
     <span class="match-scroller__day">19</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Sep</span>
     <span class="match-scroller__day">20</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Sep</span>
     <span class="match-scroller__day">21</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Sep</span>
     <span class="match-scroller__day">22</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Sep</span>
     <span class="match-scroller__day">23</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Sep</span>
     <span class="match-scroller__day">24</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Sep</span>
     <span class="match-scroller__day">25</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Sep</span>
     <span class="match-scroller__day">26</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Sep</span>
     <span class="match-scroller__day">27</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Sep</span>
     <span class="match-scroller__day">28</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Sep</span>
     <span class="match-scroller__day">29</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Sep</span>
     <span class="match-scroller__day">30</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">1</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">2</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">3</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">4</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">5</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">6</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">7</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">8</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">9</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">10</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">11</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">12</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">13</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">14</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">15</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">16</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">17</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">18</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">19</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">20</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">21</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">22</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">23</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">24</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">25</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">26</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">27</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">28</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">29</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">30</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Oct</span>
     <span class="match-scroller__day">31</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Nov</span>
     <span class="match-scroller__day">1</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Nov</span>
     <span class="match-scroller__day">2</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Nov</span>
     <span class="match-scroller__day">3</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Nov</span>
     <span class="match-scroller__day">5</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Nov</span>
     <span class="match-scroller__day">6</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Nov</span>
     <span class="match-scroller__day">8</span>
     </h2>,
     <h2 class="match-scroller__date">
     <span class="match-scroller__month">Nov</span>
     <span class="match-scroller__day">10</span>
     </h2>]




```python
tables=my_soup('table',{'class':'standings-table standings-table--full'}) #extracting table from the page
print(len(tables))
```

    1
    


```python
headers = tables.findAll('th')
print(headers)
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-19-3ace73a59433> in <module>
    ----> 1 headers = tables.findAll('th')
          2 print(headers)
    

    c:\users\rakes\appdata\local\programs\python\python38\lib\site-packages\bs4\element.py in __getattr__(self, key)
       2171     def __getattr__(self, key):
       2172         """Raise a helpful exception to explain a common code fix."""
    -> 2173         raise AttributeError(
       2174             "ResultSet object has no attribute '%s'. You're probably treating a list of elements like a single element. Did you call find_all() when you meant to call find()?" % key
       2175         )
    

    AttributeError: ResultSet object has no attribute 'findAll'. You're probably treating a list of elements like a single element. Did you call find_all() when you meant to call find()?



```python

```
