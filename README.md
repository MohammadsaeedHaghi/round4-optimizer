<p align="center">
  <a href="" rel="noopener">
 <img src="http://optimizer.math.sharif.edu/wp-content/uploads/2021/02/optimizer.png" alt="Optimizer logo"></a>
</p>
<h3 align="center">رندوم نویز میکرز</h3>

<div align="center">

  [![Status](https://img.shields.io/badge/status-active-success.svg)]() 
  [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/mtefagh/demos/HEAD)
  [![License](https://img.shields.io/badge/license-GPL-blue.svg)](https://github.com/mtefagh/demos/blob/master/LICENSE)

</div>

---

<p align="center"> معرفی و توضیح مختصر روش استفاده شده و در صورت تمایل بج‌هایی که علاقه‌مند هستید را به جای بج‌های بالا جایگزین کنید
    <br> 
    برای خوشه‌بندی از spectral clustering استفاده شد. 
    برای تشخیص داده پرت در این بخش با استفاده از pca و دستی این‌کار را انجام شد.
    برای پیدا کردن بعد از pca استفاده شد. (drop off)
</p>

## 📝 فهرست مطالب
- [صورت‌بندی سوال](#problem_statement)
- [الگوریتم بهینه‌سازی](#idea)
- [محدودیت‌ها](#limitations)
- [ایده‌های گسترش](#future_scope)
- [روند اجرا](#getting_started)
- [نحوه استفاده](#usage)
- [وابستگی‌ها](#tech_stack)
- [نویسندگان](#authors)
- [قدردانی](#acknowledgments)

## 🧐 صورت‌بندی سوال <a name = "problem_statement"></a>
فرمول‌بندی سوال بهینه‌سازی حل شده در کد و اشاره به تقریب‌هایی که از سوال اصلی زده‌اید تا به سوال مورد نظر برسید

به جز فرض‌های اولیه داده شده در این بخش تقریب خاصی نزده ایم. یافتن منیفولدها و مرکز و شعاع بهینه به همراه بعد.


## 💡 الگوریتم بهینه‌سازی <a name = "idea"></a>
روش حل عددی سوال مدل‌سازی شده در قسمت قبل را توضیح و یا به منبعی که از آن استفاده کرده‌اید ارجاع دهید

برای پیدا کردن منیفولدها از Spectral Clustering استفاده شد.

برای پیدا کردن مرکز و شعاع بهینه نیز از الگوریتم iterative زیر استفاده شد:
```
1. choose a random point as the center of the manifold (we chose mean of the points) (c)
2. find the point with the maximum distance from the chosen center (p)
3. update c with the below equation:
  c = c + lambda * (p - c)
```

برای تشخیص بعد هم از drop off زیاد در مقدار explained_variance در pca استفاده کردیم.
## ⛓️ محدودیت‌ها <a name = "limitations"></a>
اگر روش شما صرفا در شرایط خاصی کار می‌کند فرض‌های مورد نیاز برای به درستی جواب دادن آن را بیان کنید. هم‌چنین در صورت وجود، به وابستگی‌های نرم‌افزاری و سخت‌افزاری مانند سیستم عامل یا کارت گرافیکی نیز در همین قسمت اشاره نمایید

محدودیت خاصی وجود ندارد.

## 🚀 ایده‌های گسترش <a name = "future_scope"></a>
پیشنهادهایی که موفق به پیاده‌سازی آن نشدید ولی در آینده بر پایه همین کد فعلی قابل اضافه کردن می‌باشند

در این مرحله نکته خاصی وجود ندارد.
## 🏁 روند اجرا <a name = "getting_started"></a>
چگونه کد شما را می‌توان تست نمود؟

ترجیحا از colab استفاده شود و cell ها به صورت متوالی اجرا شوند. (البته ممکن است که ترتیب اجرای لازم در یک نوتبوک در حد یکی دو cell بالا پایین شده باشد.)
### پیش‌نیازها

اگر نیاز به نصب نرم‌افزار یا ایجاد محیط خاصی برای اجرای کد هست، مراحل نصب پیش‌نیازها را قدم به قدم توضیح دهید

کد را در محیط google colab ترجیحا اجرا کنید.

### نصب

اگر خود کد شما نیاز به نصب دارد مراحل نصب پکیج خود را قدم به قدم توضیح دهید

برای همگی از دستور pip install استفاده کیند.

(اگر از colab استفاده کنید صرفا نیاز به نصب تعداد محدودی کتابخانه خواهید شد که کد نصبشان در خود کد آمده است)

## 🎈 نحوه استفاده <a name="usage"></a>
ورودی و خروجی توابع و این که آن‌ها را چگونه (با چه سینتکسی) باید صدا زد

کافی است نام فایل را در cell مربوط به خواندن فایل درست دهید.
(cell که از with استفاده کرده است.)
مثلا:

```
import numpy as np
with open("R11.txt", "r") as f:
  d, n, m, k, p = [-1 if x == "_" else int(x) for x in f.readline().split()]
  ks = [int(x) for x in f.readline().split()]
  data = [[float(x) for x in string.split()] for string in f.readlines()]
  data = np.array(data)

data.shape
```

## ⛏️ وابستگی‌ها <a name = "tech_stack"></a>
لیست تمام زبان‌های برنامه‌نویسی، پکیج‌ها و کتاب‌خانه‌های استفاده شده

```
sklearn
numpy
matplotlib
skdim
pyod
```

## ✍️ نویسندگان <a name = "authors"></a>
لیست نام نویسندگان به تفکیک هر قطعه (تابع، فایل، ...) از کد
مهدی سلمانی و محمدسعید حقی (به صورت همزمان)

## 🎉 قدردانی <a name = "acknowledgments"></a>
تشکر از هر کسی که به نحوی در گسترش این کد به شما کمک کرده است
