1.swiper 自定义效果
最终效果:

![](/assets/swiper-effect-01.gif)

```js
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <script src="libs/jquery/jquery-3.1.0.min.js"></script>
  <script src="libs/swiper/js/swiper.min.js"></script>
  <link rel="stylesheet" href="libs/swiper/css/swiper.min.css">
</head>
<body>
<div class="service-part04">
  <div class="center w1100">
    <div class="student-swiper">
      <div class="student-swiper-container swiper-container-horizontal">
        <div class="swiper-wrapper" style="transition-duration: 0ms; transform: translate3d(-3247px, 0px, 0px);">
          <div class="swiper-slide swiper-slide-duplicate" data-swiper-slide-index="0"
               style="transform: translateX(6762.6px) scale(-0.8); z-index: 909; opacity: 0;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
          <div class="swiper-slide swiper-slide-duplicate" data-swiper-slide-index="1"
               style="transform: translateX(5480.8px) scale(-0.6); z-index: 919; opacity: 0;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
          <div class="swiper-slide swiper-slide-duplicate" data-swiper-slide-index="2"
               style="transform: translateX(4331.6px) scale(-0.4); z-index: 929; opacity: 0;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
          <div class="swiper-slide swiper-slide-duplicate swiper-slide-duplicate-prev" data-swiper-slide-index="3"
               style="transform: translateX(3315px) scale(-0.2); z-index: 939; opacity: 0;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
          <div class="swiper-slide swiper-slide-duplicate swiper-slide-duplicate-active" data-swiper-slide-index="4"
               style="transform: translateX(2431px) scale(0); z-index: 949; opacity: 0;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
          <div class="swiper-slide swiper-slide-duplicate-next" data-swiper-slide-index="0"
               style="transform: translateX(1679.6px) scale(0.2); z-index: 959; opacity: 0;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
          <div class="swiper-slide" data-swiper-slide-index="1"
               style="transform: translateX(1060.8px) scale(0.4); z-index: 969; opacity: 1;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
          <div class="swiper-slide" data-swiper-slide-index="2"
               style="transform: translateX(574.6px) scale(0.6); z-index: 979; opacity: 1;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
          <div class="swiper-slide swiper-slide-prev" data-swiper-slide-index="3"
               style="transform: translateX(221px) scale(0.8); z-index: 989; opacity: 1;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
          <div class="swiper-slide swiper-slide-active" data-swiper-slide-index="4"
               style="transform: translateX(0px) scale(1); z-index: 999; opacity: 1;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
          <div class="swiper-slide swiper-slide-duplicate swiper-slide-next" data-swiper-slide-index="0"
               style="transform: translateX(-221px) scale(0.8); z-index: 989; opacity: 1;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
          <div class="swiper-slide swiper-slide-duplicate" data-swiper-slide-index="1"
               style="transform: translateX(-574.6px) scale(0.6); z-index: 979; opacity: 1;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
          <div class="swiper-slide swiper-slide-duplicate" data-swiper-slide-index="2"
               style="transform: translateX(-1060.8px) scale(0.4); z-index: 969; opacity: 1;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
          <div class="swiper-slide swiper-slide-duplicate swiper-slide-duplicate-prev" data-swiper-slide-index="3"
               style="transform: translateX(-1679.6px) scale(0.2); z-index: 959; opacity: 0;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
          <div class="swiper-slide swiper-slide-duplicate swiper-slide-duplicate-active" data-swiper-slide-index="4"
               style="transform: translateX(-2431px) scale(0); z-index: 949; opacity: 0;">
            <div class="swiper-slide-img">
              <img src="img/daogou.png" alt="">
            </div>
          </div>
        </div>
        <span class="swiper-notification" aria-live="assertive" aria-atomic="true"></span></div>
      <script>
        $(function () {
          new Swiper('.student-swiper .student-swiper-container', {
            watchSlidesProgress: true,
            slidesPerView: 'auto',
            centeredSlides: true,
            loop: true,
            loopedSlides: 5,
            autoplay: {
              delay: 5000,
              stopOnLastSlide: false,
              disableOnInteraction: true,
            },
            on: {
              progress: function () {
                for (i = 0; i < this.slides.length; i++) {
                  var slide = this.slides.eq(i);
                  var slideProgress = this.slides[i].progress;
                  modify = 1;
                  if (Math.abs(slideProgress) > 1) {
                    modify = (Math.abs(slideProgress) - 1) * 0.3 + 1;
                  }
                  //长度 221是每个swiper-slide宽度的一半
                  translate = slideProgress * modify * 221 + 'px';
                  scale = 1 - Math.abs(slideProgress) / 5;
                  zIndex = 999 - Math.abs(Math.round(10 * slideProgress));
                  slide.transform('translateX(' + translate + ') scale(' + scale + ')');
                  slide.css('zIndex', zIndex);
                  slide.css('opacity', 1);
                  if (Math.abs(slideProgress) > 3) {
                    slide.css('opacity', 0);
                  }
                }
              },
              setTransition: function (transition) {
                for (var i = 0; i < this.slides.length; i++) {
                  var slide = this.slides.eq(i);
                  slide.transition(transition);
                }
              }
            }
          })
        })
      </script>
    </div>
  </div>
</div>

<style>
  .student-swiper {
    position: relative;
  }

  .student-swiper-container {
    position: relative;
    overflow: hidden;
  }

  .swiper-slide {
    width: 442px;
    text-align: center;
    line-height: 2em;
  }

  .swiper-slide-img {
    height: 276px;
    overflow: hidden;
    background: #fff;
  }

  img {
    width: 100%;
  }
</style>

</body>
</html>
```


