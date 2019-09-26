![Build Status](https://gitlab.com/shirazlug/shirazlug.gitlab.io/badges/master/build.svg)

---
## داستان ما

 اعضای جامعه ی کاربری شیرازلاگ تصمیم گرفتند تا توسعه سایت را
 به گیت لب و سرویس صفحات آن منتقل کنند.

برخی از این نیاز ها عبارت اند از:

- آسانی در مشارکت همگانی
- انعطاف پذیری و کنترل بالا در توسعه
- مزایای استفاده از یک سیستم مدیریت نسخه مانند گیت(git)


---
## توسعه دهندگان سایت

 این پروژه به لطف همه کسانی توسعه داده شده است که به صورت داوطلبانه و بدون دریافت هیچگونه هزینه ای، به اشتراک دانش و خلاقیت خود پرداخته اند. شما هم می توانید به توسعه این سایت کمک کنید و در لیست توسعه دهندگان قرار بگیرید.

---

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**فهرست مطالب** 

1. [چگونه میتوانید کمک کنید؟](#%DA%86%DA%AF%D9%88%D9%86%D9%87-%D9%85%DB%8C%D8%AA%D9%88%D8%A7%D9%86%DB%8C%D8%AF-%DA%A9%D9%85%DA%A9-%DA%A9%D9%86%DB%8C%D8%AF%D8%9F)
2. [سرویس گیت لب سی آی](#%D8%B3%D8%B1%D9%88%DB%8C%D8%B3-%DA%AF%DB%8C%D8%AA-%D9%84%D8%A8-%D8%B3%DB%8C-%D8%A2%DB%8C)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


# ۱- چگونه میتوانید کمک کنید؟

## نحوه ی کار با پروژه بر روی کامپیوتر شخصی
برای کار کردن بر روی این پروژه از طریق کامپیوتر شخصی، کافی است مراحل زیر را دنبال کنید:

  1. از این پروژه یک نسخه بر روی سیستم کامپیوتری خود ذخیره کنید (Fork / Clone / Download).
  2. **هیوگو** را نصب کنید.
  3. با استفاده از دستور 
  `hugo server`
  در مسیر پروژه، وب سایت را مشاهده کنید.
  4. محتوای لازم را به سایت اضافه کنید یا تغییر دهید.
  5. با استفاده از دستور 
  `hugo`
  سایت را تولید کنید (غیر لازم برای این پروژه).

برای مطالعه ی بیشتر برای کار با هوگو به وبسایت آن مراجعه کنید. 

### پیش نمایش وبسایت

در صورتی که این پروژه را بر روی کامپیوتر شخصی خود ذخیره کنید و در مسیر پروژه، دستور
`hugo server`
را بزنید، سایت شما در آدرس
`localhost:1313/`
قابل مشاهده خواهد بود.

# ۲- سرویس گیت‌لب سی‌آی

صفحات ایستای این پروژه با استفاده از 
**گیت لب سی آی**
تولید شده اند. مراحل اجرایی تعریف شده در فایل 
[`.gitlab-ci.yml`](.gitlab-ci.yml)
را در ادامه مشاهده می کنید.

<div dir="ltr">
    
    image: monachus/hugo

    variables:
      GIT_SUBMODULE_STRATEGY: recursive

    test:
      script:
      - hugo
      except:
      - master

    pages:
      script:
      - hugo
      artifacts:
        paths:
        - public
      only:
      - master
      


