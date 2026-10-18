# RPLIDAR A3M1 ile ROS 2 Üzerinde 2D SLAM

Slamtec **RPLIDAR A3M1** kullanarak **Ubuntu 22.04 + ROS 2 Humble** üzerinde, tekerlek veya encoder kullanmadan 2D SLAM haritası oluşturma rehberi.

Bu projede LiDAR fiziksel olarak elde taşınarak hareket ettiriliyor. Hareket bilgisi **rf2o_laser_odometry** ile LiDAR taramalarından çıkarılıyor ve **slam_toolbox** ile birleştirilerek gerçek ortamın 2D haritası oluşturuluyor.

## 🎥 Video

📺 **YouTube:**  
https://www.youtube.com/watch?v=cde0imSBgng

Videoda tüm kurulum ve SLAM süreci adım adım gösterilmektedir.

## 🧩 Kullanılan Sistem

- Ubuntu 22.04
- ROS 2 Humble
- Slamtec RPLIDAR A3M1
- SLLIDAR ROS 2 Driver
- rf2o Laser Odometry
- slam_toolbox
- RViz2
- Nav2 Map Server

## 🔄 Sistem Akışı

```text
RPLIDAR A3M1
     │
     ▼
   /scan
     │
     ▼
rf2o_laser_odometry
     │
     ▼
   /odom
     │
     ▼
 slam_toolbox
     │
     ▼
    /map
     │
     ▼
   RViz2
```

## 🚀 Bu Rehberde Neler Var?

- RPLIDAR A3M1'i Ubuntu'ya bağlama
- ROS 2 Humble ortamını hazırlama
- SLLIDAR ROS 2 sürücüsünü kurma
- `/scan` verisini kontrol etme
- LiDAR verisini RViz2 üzerinde görüntüleme
- `dialout` seri port izinlerini ayarlama
- `rf2o_laser_odometry` ile LiDAR tabanlı odometri oluşturma
- `base_link → laser` TF bağlantısını oluşturma
- `base_link → base_footprint` TF bağlantısını oluşturma
- `slam_toolbox` ile gerçek zamanlı SLAM yapma
- RViz2 üzerinde `/map` ve `/scan` verilerini görüntüleme
- Oluşturulan haritayı `.pgm` ve `.yaml` olarak kaydetme
- SLAM sırasında karşılaşılabilecek yaygın hataları çözme

## 🗺️ Sonuç

Bu çalışmanın sonunda herhangi bir tekerlek, encoder veya hazır robot platformu kullanmadan, yalnızca LiDAR taramalarından yararlanarak ev/oda ölçeğinde bir **2D SLAM haritası** oluşturulmaktadır.

> ⚠️ **Önemli:** Haritalama sırasında LiDAR mümkün olduğunca yatay tutulmalı ve yavaş hareket ettirilmelidir. Hızlı dönüşler ve LiDAR'ın eğilmesi odometri ve harita kalitesini ciddi şekilde etkileyebilir.



## 🔮 Sonraki Aşama

Bu çalışmanın sonraki aşamasında:

- Birden fazla terminalde manuel olarak çalıştırılan süreçlerin
- Tek bir **ROS 2 launch dosyası** altında toplanması
- Ardından **encoder'lı tekerlekli robot platformuna** geçilmesi

planlanmaktadır.

## 📝 Not

Bu repository öncelikli olarak eğitim ve dokümantasyon amacıyla hazırlanmıştır. Amaç, RPLIDAR A3M1 kullanarak ROS 2 üzerinde LiDAR tabanlı odometri ve 2D SLAM sürecini adım adım göstermektir.

---

**ROS 2 • LiDAR • SLAM • Robotics**
