## How to use Swiper js for beginners with react js 

### First Step(Installation):
 ``` npm install --save swiper@6.4.1 ```
 
### Second Step(import the necessary file below):
``` js
import React, { useEffect } from 'react'; 
import SwiperCore, {
  EffectCoverflow,
  Pagination,
  Autoplay,
  Navigation,
} from 'swiper'; 
import { Swiper, SwiperSlide } from 'swiper/react'; 
import 'swiper/swiper-bundle.min.css'; 

SwiperCore.use([EffectCoverflow, Pagination, Autoplay, Navigation]); 

const slide_img = [
  "https://swiperjs.com/demos/images/nature-1.jpg",
  "https://swiperjs.com/demos/images/nature-2.jpg",
  "https://swiperjs.com/demos/images/nature-3.jpg",
  "https://swiperjs.com/demos/images/nature-4.jpg",
  "https://swiperjs.com/demos/images/nature-5.jpg",
  "https://swiperjs.com/demos/images/nature-6.jpg",
  "https://swiperjs.com/demos/images/nature-7.jpg",
  "https://swiperjs.com/demos/images/nature-8.jpg",
  "https://swiperjs.com/demos/images/nature-9.jpg",
]; 

const MySwiperSlider = () => {
  useEffect(() => {
    const swiper = new SwiperCore('.mySwiper', {
      effect: 'slide',
      grabCursor: true,
      centeredSlides: 0,
      slidesPerView: 3, // Display 3 images per slide
      spaceBetween: 20, // Space between each image
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      },
      autoplay: {
        delay: 2000, // Delay between slides (in milliseconds)
        disableOnInteraction: false, // Allow autoplay to continue on user interaction
      },
      breakpoints: {
        // Responsive breakpoints
        250:{
          slidesPerView: 1,
        },
        379:{
          slidesPerView: 1,
        },
        380: {
          slidesPerView: 2,
        },
        480: {
          slidesPerView: 2,
        },
        565: {
          slidesPerView: 3,
        },
        768: {
          slidesPerView: 4,
        },
        1024: {
          slidesPerView: 5,
        },
      },
    });

    // Clean up Swiper instance on unmount
    return () => {
      swiper.destroy();
    };
  }, []);

  return (
    <div>
      <Swiper className="mySwiper">
        {slide_img.map((img, i) => (
          <SwiperSlide key={i}>
              <img src={img} alt="" />
            </SwiperSlide>
        ))}
        <div className="swiper-button-next"></div>
        <div className="swiper-button-prev"></div>
      </Swiper>
    </div>
  );
};

export default MySwiperSlider;
```
#### **NOTE:**
When you work on the local file then you can use the update swiper js package. Else, if you code on stackblitz you use this code. The code is fully responsive.
