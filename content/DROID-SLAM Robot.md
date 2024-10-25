- [ ] Get Citations
- [ ] Cite diagram
- [ ] Cite Formulae
- [ ] Add IMage of esp32, jetson nano

Introduction
- Couple of algorithms in the wild
- Challenges
- Type of algorithms and the various inputs they take
- Those algorithms might not work on limited resource applications


Embedded Mobile ROS Platform for SLAM Application with RGB-D Cameras - http://ecasp.ece.iit.edu/publications/2012-present/2020-04.pdf

Edge-SLAM: Edge-Assisted Visual Simultaneous Localization and Mapping- https://dl.acm.org/doi/pdf/10.1145/3561972

- [A Comparative Analysis of LiDAR SLAM-Based Indoor Navigation for Autonomous Vehicles]( https://www.researchgate.net/profile/Qin-Zou-3/publication/350160955_A_Comparative_Analysis_of_LiDAR_SLAM-Based_Indoor_Navigation_for_Autonomous_Vehicles/links/654a0badce88b87031d1a58a/A-Comparative-Analysis-of-LiDAR-SLAM-Based-Indoor-Navigation-for-Autonomous-Vehicles.pdf) 
- [SuMa++: Efficient LiDAR-based Semantic SLAM](https://arxiv.org/pdf/2105.11320)
- [F-LOAM : Fast LiDAR Odometry and Mapping](F-LOAM : Fast LiDAR Odometry and Mapping)
- [A Surveillance Mobile Robot based on Low-Cost Embedded Computers](https://www.researchgate.net/profile/Emanuele-Secco/publication/359711438_A_Surveillance_Mobile_Robot_based_on_Low-Cost_Embedded_Computers/links/633c4fc4ff870c55cefe2ed0/A-Surveillance-Mobile-Robot-based-on-Low-Cost-Embedded-Computers.pdf)
- [Embedded Mobile ROS Platform for SLAM Application with RGB-D Cameras](http://ecasp.ece.iit.edu/publications/2012-present/2020-04.pdf)
- [Edge-SLAM: Edge-Assisted Visual Simultaneous Localization and Mapping](https://dl.acm.org/doi/pdf/10.1145/3561972)


System:
![[IMG_2023.png]]

![[IMG_2250.png]]
>[!Info]Note:
>The USB to TTL is the same as the FTDI component

![[Pasted image 20241001103240.png]]

![[Pasted image 20241001103300.png]][![PCA9685 16 channel 12 bit PWM servo driver for Raspberry Pi](https://cdn.shopify.com/s/files/1/1509/1638/products/pca9685-16-kanal-12-bit-pwm-servotreiber-fur-raspberry-pi-359254.jpg?v=1679399065)![PCA9685 16 channel 12 bit PWM servo driver for Raspberry Pi](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ2Eo02ZyhS-Nyw9oaP6jshuppup1e5YKQochqGth8P7BAfWBY4AM_2y7A8F4V7_GwogIc&usqp=CAU)](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.az-delivery.uk%2Fproducts%2Fpca9685-servotreiber&psig=AOvVaw10dSn_ZIWi59cYRtX_arXF&ust=1728370019543000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCOiFoprW-4gDFQAAAAAdAAAAABAP)

[![How to use PCA9685 16-Channel 12-Bit PWM Servo Driver with ...](https://mytectutor.com/wp-content/uploads/2021/09/PCA9685-16-channel-servo-motor-driver-pinout.jpg)
[![Digital Town - PCA685 and LED's](https://digitaltown.co.uk/images/components/PCA9685/PCA9685pinout.jpg)![Digital Town - PCA685 and LED's](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRG3UA2Qy2KQ8da-sADS_zZqifwQv6z6qJ_xA&s)](https://www.google.com/url?sa=i&url=https%3A%2F%2Fdigitaltown.co.uk%2Fcomponents16-PCA9685LED.php&psig=AOvVaw10dSn_ZIWi59cYRtX_arXF&ust=1728370019543000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCOiFoprW-4gDFQAAAAAdAAAAABAc)

## 19 October
Tried to fix the 3d printer problem today. I have an issue setting up klipper and mainsailos on rpi zero 2w, as my old raspberry pi 4b stopped working. I will try to fix it soon, but I always wanted to integrate the rpi zero 2w into the board of the 3d printer, since it uses much less power and heats up way less, and is the correct form factor to be embedded into the printer. This saves me a usb port both on the printer and the pi. My other projects are blocked because of this hurdle because I need to be able to print the legs for the hexapod


## Setting up ORB-SLAM
## Installing Pangolin
[[Pangolin]] is a set of lightweight and portable utility libraries for prototyping 3D, numeric or video based programs and algorithms, used in Computer Vision as a means to remove platform-specific boilerplate and make it easy to visualize data.
To install [[Pangolin]]:
```bash
git clone --recursive https://github.com/stevenlovegrove/Pangolin.git

# Override the package manager choice and install all packages
./scripts/install_prerequisites.sh -m brew all
```
### Installing OpenCV
You can install opencv using two methods:
1. Build from source (access to cutting edge releases)
2. Via Homebrew (quicker and simpler)

To install openCV on mac:
```bash
git clone https://github.com/opencv/opencv.git                                 
```
Since opencv doesn't allow [[CMake#In-source builds|in-source builds]], we will have to do build it into a directory thats outside the source tree. So create a folder outside of the opencv git repository and use `cmake` to build the opencv codebase, specifying source directory using `-S` and build directory using `-B`, and then finally build using `make`:

```bash
mkdir build_opencv                                                     ─╯
cmake -DCMAKE_BUILD_TYPE=Release -DBUILD_EXAMPLES=ON -B~/Code/build_opencv -S~/Code/opencv
make -j7 # runs 7 jobs in parallel
```

>[!INFO] Note:
>We want to to build the project with the examples, hence the `-DBUILD_EXAMPLES=ON`

