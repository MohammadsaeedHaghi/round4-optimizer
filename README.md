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


به جز فرض‌های اولیه داده شده در این بخش تقریب خاصی نزده ایم. یافتن منیفولدها و مرکز و شعاع بهینه به همراه بعد.


## 💡 الگوریتم بهینه‌سازی <a name = "idea"></a>
ایتدا بوسیله Umap و pca بعد داده ها کاهش داده شد.
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
به علت محدودیت حجم خروجی مجبور به حدف کردن دادههای آفین از این بخش شدیم.
## 🚀 ایده‌های گسترش <a name = "future_scope"></a>
میتوان با توجه توضیحاتی که در قسمت توضیح مشروح آورده شده است، تعدادی از کلاسترها را بهم پیوند زد تا تشکیل یک منیفلد دهند.
## 🏁 روند اجرا <a name = "getting_started"></a>


ترجیحا از colab استفاده شود و cell ها به صورت متوالی اجرا شوند. (البته ممکن است که ترتیب اجرای لازم در یک نوتبوک در حد یکی دو cell بالا پایین شده باشد.)
### پیش‌نیازها

اگر نیاز به نصب نرم‌افزار یا ایجاد محیط خاصی برای اجرای کد هست، مراحل نصب پیش‌نیازها را قدم به قدم توضیح دهید

کد را در محیط google colab ترجیحا اجرا کنید.

### نصب

اگر خود کد شما نیاز به نصب دارد مراحل نصب پکیج خود را قدم به قدم توضیح دهید

برای همگی از دستور pip install استفاده کیند.

(اگر از colab استفاده کنید صرفا نیاز به نصب تعداد محدودی کتابخانه خواهید شد که کد نصبشان در خود کد آمده است)

## 🎈 نحوه استفاده <a name="usage"></a>


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

```
sklearn
numpy
matplotlib
skdim
pyod
```

## ✍️ نویسندگان <a name = "authors"></a>
 از کد
مهدی سلمانی و محمدسعید حقی (به صورت همزمان)

## 🎉 قدردانی <a name = "acknowledgments"></a>

