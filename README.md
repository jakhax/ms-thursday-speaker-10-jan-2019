# Having Fun With Computers 
---------------------------

> **Truth is: anything you do, any tutorial you follow, any project you start and never finish, any dead end that you head down, it's not wasted. It's all experience that is accumulating over time.**

This is repo contains references and notes about a presentation we ([reivhax](https://github.com/reivahax) & [jakhak](https://github.com/jakhax)) did at [Moringa School](https://moringaschool.com) on 10th Jan 2019, which is basically some of the projects we have done to learn how computers work at the same time building something fun.

This is the link to the [Presentation Slides](https://docs.google.com/presentation/d/1ca6mX68-P9KtuZuqDCryVN3aiNYsFBOipO5SeM2in1M/edit?usp=sharing).

## Table of contents
* [Fun with DIY electronics and Hardware Programming](#fun-with-diy-electronics-and-hardware-programming)
    * [Visualizing Music on an LED strip using Esp8266](#visualizing-music-on-an-led-strip-using-esp8266)
    * [Making a simple smart home using Raspberry Pi](#making-a-simple-smart-home-using-raspberry-pi)
    * [Telegram bot to locate objects using Esp8266](#telegram-bot-to-locate-objects-using-esp8266)
    * [FAQs-getting started with DIY electronics and hardware programming](#faqs-getting-started-with-diy-electronics-and-hardware-programming)
* [Mentionable AI projects we have done](#mentionable-ai-projects-we-have-done)
   * [Shamba Doctor](#shamba-doctor)
   * [sonic the self-driving car](#sonic-the-self-driving-car)
   * [Telegram bot to find celeb look alikes](#'telegram-bot-to-find-celeb-look-alikes')
   * [FAQs AI and Machine Learning](#faqs-we-got-asked-about-ai-and-machine-learning)
   
* [Just a little chat about hacking and CTFs](#just-a-little-chat-about-hacking-and-ctfs)
   * [Simple Exploit Examples](#simple-exploit-examples)
   * [CTFs](#ctf)
   * [CTF resourses](#ctf-resources)
   * [FAQs Hacking & CTFs](#faqs-we-were-asked-about-hacking-and-ctfs)
* [Any other random stuff](#any-other-random-stuff)
* [Contributing](#contributing)
* [Contacts](#contacts)

# Fun with DIY electronics and Hardware Programming

## [Visualizing Music on an LED strip using Esp8266](https://github.com/jakhax/Esp8266-Audio-Reactive-Web-Controlled-LED-Strip)

<img src="media/led-effect-demo.gif"  >

- In this project we did audio visualization on an LED strip i.e the [ws2812 adafruit neopixels]() using a computer for audio processing which sends the data to the [esp8266](https://tttapa.github.io/ESP8266/Chap01%20-%20ESP8266.html) via wifi which then visualizes it on the LED strip.
- Check out the [repo](https://github.com/jakhax/Esp8266-Audio-Reactive-Web-Controlled-LED-Strip) containing the project to see how it works and resources to learning materials.

<img src="media/audio-visualization-desc.gif"  alt="Circuit Image" width="600" height="300">

## [Making a simple smart home using Raspberry Pi](https://github.com/jakhax/smart-home)

In this project we made a working model of a smart home using the [raspberry pi](https://www.makeuseof.com/tag/9-things-wanted-know-raspberry-pi/).The project consists of three logical parts: `front end`,`back end` and `hardware units`.

### Front-end 
- The front-end was made using [Angular 6](https://cli.angular.io/).
- We were also able to make a `mobile app` for this using [Cordova](https://cordova.apache.org/) and a `desktop app` for windows, mac os & linux using [electron js](https://electronjs.org/), details are in the original [repo](https://github.com/jakhax/smart-home).
- It consists of an interactive svg file that you can click on to select different rooms of the home then interact with the devices in those rooms.
- The user must be authenticated to use the app, so user accounts must first be created from the back-end by the home admin.

<img src="media/smart-rooms.png"  alt="Smart Home Interface" width="600" height="300">

### Back-end 
- Made using [django](https://www.djangoproject.com/) web framework, and is hosted on the raspberry pi.
- user is first authenticated via [ django JWT](https://medium.com/python-pandemonium/json-web-token-based-authentication-in-django-b6dcfa42a332). 
- Receives authenticated commands from the front-end and runs them on the raspberry pi control connected devices.
- Admin user is also able new devices & sensors into the house through the admin interface.

### Hardware
- This part entails the devices & sensors connected that become part of the homes [IOT](https://en.wikipedia.org/wiki/Internet_of_things).
- We were able to control devices and get data from sensors e.g light bulbs, fans, air conditioner, humidity & temp sensors, home media system.
- below is an image of the circuit connection we used, everything is controlled over the home network to which the raspberry pi is connected to.
<img src="media/smart-home-circuit.png"  alt="Circuit Image" width="400" height="200">

## [Telegram bot to locate objects using Esp8266]()
- `@todo`: publish project to github and document by @reivhax

## FAQs-getting started with DIY electronics and hardware programming
- **How do i even get started with this stuff?**
    - We would recommend you to get a starters kit for either [arduino]() or [raspberry pi]() that includes everything you need, in DIY you really have to gets your hands dirty to understand how things work.
    - starters kits can start you on your way to working with everything from Arduino to robotics.
    - Alternatively, you can also take online classes or follow tutorials to learn the basics of your electronics. [Adafruit](https://learn.adafruit.com/) has a huge collection of tutorials. Some people also post their DIY projects on [hackster.io](https://www.hackster.io), [instructables](https://www.instructables.com) and [hackaday](https://hackaday.com/)
    - Talk to someone who knows and visit hacker spaces, this can save you a lot of time.
    - Awesome articles about `how to get started with DIY electronics`.
        - https://www.makeuseof.com/tag/get-started-diy-electronic-projects-learning-sites/
        - https://learn.sparkfun.com/tutorials/where-do-i-start/all
        - https://lifehacker.com/5975190/how-to-get-started-with-diy-electronics-projects
        - https://www.circuito.io/blog/diy-electronics-best-online-tools/

- **Am from Kenya, where do i buy the starters kits or other DIY electronics stuff locally?**
    - check out the following dealers, they also do shipping, search for stuff you need on their websites.
        - [Nerokas Engineering](https://store.nerokas.co.ke)
        - [Ktechnics](https://ktechnics.com)

- **Do i need to learn advance physics & maths to do DIY electronics?**
    - Simply no, the concepts needed to do DIY electronics can be easliy learnt, ofcourse you will need to first learn how electricity works, but most of this just requires the will to learn how things work,growth mentality, its way easier and much fun compared to web development.
- **Am interested in programming the Esp8266 with python, where  should i start?**
    - I wrote a comprehensive article on medium on how to get startd with the Esp8266 using Micropython
        - https://medium.com/@jackogina60/getting-started-with-micropython-on-esp8266-32eba914fed2
    - [Official docs](http://docs.micropython.org/en/latest/)

- **Yo! so you mentioned the Audio visualization project had some math in it,where can I get started?**
    - You can start by looking at Fast Fourier Transformation, [3blue 1brown](https://www.youtube.com/channel/UCYO_jab_esuFRV4b17AJtAw) made an awesome video on it that is beginners friendly.
    - Learning how to use the [numpy](http://www.numpy.org/) library in python to do array operations would also help.
    - Read the visualization code in the [repo](https://github.com/jakhax/Esp8266-Audio-Reactive-Web-Controlled-LED-Strip)
    - Learning a bit of [calculus](https://www.youtube.com/playlist?list=PLZHQObOWTQDMsr9K-rj53DwVRMYO3t5Yr) may prove usefull when working with audio visualization


# Mentionable AI projects we have done

## [Shamba Doctor]()
- @reivhax to document this part

## [Sonic the self-driving car](https://github.com/jakhax/sonic-the-self-driving-car)
- We made a self driving [RC car](https://en.wikipedia.org/wiki/Radio-controlled_car) for robots racing competitions, that could autopilot itself on the racing lane, controlling both throttling and steering.
- The end goal was just to have fun while at the same time understand how self driving cars work from scratch meaning pre-existing software like [R.O.S](http://www.ros.org/) was not an option for us.

- There is an existing project called [Donkey Car](http://www.donkeycar.com/) that is a great reference for learning self driving cars from scratch using deep learning, the main reason we did not use [Donkey Car](http://www.donkeycar.com/) was because the hardware items required was either too expensive for us or just unavailable hence we had to write our own software, though we learnt a lot from the [Donkey Car](http://www.donkeycar.com/) project.


 ### Hardware used
 1. Raspberry Pi - where we run the car's firmware on.
 2. Car chasis - we bought [this](https://store.nerokas.co.ke/index.php?route=product/product&product_id=1808&search=chassis&description=true) chasis nerokas that comes with a dc motor for throttling and a servo motor for steering
 3. Pi camera
 4. Lipo battery for the car and a 5v power bank for the Pi.
 5. L298n dc motor driver

- We used [nvidia's research](https://devblogs.nvidia.com/deep-learning-self-driving-cars/) on end to end deep learning to design our neural network, using python's tensorflow.
- We then used behavioral learning i.e. save the camera images with the corresponding steering angles and throttle values in a file for supervised learning.
- We trained our neural network using videos from driving it on our ribbon based race track and later using the [Donkey Car simulator](https://docs.donkeycar.com/guide/simulator/) made using Unity .

<img src="media/donkey-car-simulator.gif"  alt="Donkey Car simulator" width="500" height="250">

- For the web interface we used `tornado` web framework, to stream the video feed to the browser over a web socket connection, the user can use a joystick gamepad to control the vehicle during training.
- Visit the [repo](https://github.com/jakhax/sonic-the-self-driving-car) for more information about how the sonic works
- **Sonic is still a work in progress and the code base is prone to a lot of changes.**

## Telegram bot to find celeb look alikes
- @reivhax to document this part

## FAQs we got asked about AI and machine learning 
- **What resources do you recommend for learning about A.I?**
    - First of all we are literally noobs in A.I, other than the maths their is not much we know, so you may be better of learning it from a more experienced person, but here are some resources we have used.
        - [3blue 1brown neural networks series](https://www.youtube.com/watch?v=aircAruvnKk&list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi)
        - [3blue 1brown linear algebra series](https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) can act as a good refreshener for basic maths needed for machine learning.

- **Where did you learn how to make a self-driving car?**
    - In our case it was more about applying the knowlegde we had about DIY electronics to build the RC car, then reading [nvidia's research](https://devblogs.nvidia.com/deep-learning-self-driving-cars/) on end to end deep learning.
    - [udacity](https://www.udacity.com/) also has a course about self driving cars that most people recommend though i have checked it out, cause its fricking expensive, for me atleast.

# Just a little chat about hacking and CTFs
- This part was a just a general view of the cyber sec / hacking field most of the examples we showed were very basic exploits, for obvious reasons, the major take away though was to show computer programs in general can be exploited.
- In a country with very harsh cyber crime laws it will be just stupid to remind people that hacking should done legally such as in [bug bounties](https://medium.com/ehsahil/getting-started-in-bug-bounty-7052da28445a) or for educational purposes.

## Simple Exploit Examples

- Below is a list of examples that we presented just to highlight examples of very basic exploitation

1. [Malduino, making a super cheap rubber ducky](src/malduino)
2. [Simple Binary exploitation example](src/simple_binary_exploitation)
3. [Simple Server side exploitation](src/server_side_exploit_python2): Exploit server to get Avenger's endgame secrets.
4. [XSS & SQL injectio](src/xss-sql-injection-flask)
5. [XSS example](src/xss-keylogger): xss and keylogger
6. [python2 input is evil](src/python2_input_is_eval)


## CTF

CTFs are computer security/hacking competitions which generally consist of participants breaking, investigating, reverse engineering and doing anything they can to reach the end goal, a "flag" which is usually found as a string of text.

[![What is a ctf Liveoverflow video](https://img.youtube.com/vi/8ev9ZX9J45A/0.jpg)](https://www.youtube.com/watch?v=8ev9ZX9J45A)


Just like any programming challenge, take your time, learn the tools, and don't be afraid to look for help or writeups (obviously not on the CTF you're trying to achieve), but they can provide insight on tools to use, depending on the type of challenge.

CTFs are a great way of understanding not only computer security but also how computers work


### CTF resources
- [Trail of bits](https://trailofbits.github.io/ctf/) ctf guide for newbies.
- [CTF resources](https://ctfs.github.io/resources/) This repository aims to be an archive of information, tools, and references regarding CTF competitions.
- https://ctftime.org/
- [Liveoverflow](https://www.youtube.com/channel/UClcE-kVhqyiHCcjYwcpfj9w) creates lots ctf follow ups.
- [Picoctf](https://picoctf.com/) both [2017](https://2017game.picoctf.com) & [2018](https://2018game.picoctf.com/) challenges are highly recommended.
- [hackthebox](https://www.hackthebox.eu/)

## FAQs we were asked about hacking and CTFs
- **What is the secret step by step guide to learn hacking?**
    - glad you asked this. their is no guide to learn hacking, to understand an important idea i **highly recommmend** you to watch this video : [https://www.youtube.com/watch?v=2TofunAI6fU](https://www.youtube.com/watch?v=2TofunAI6fU)

- **What resources do you recommend to learn cyber security?**
    - other than **CTFs** and just **learning how computers work** by doing some practical projects and I.T stuff I really havent tried anything else, but what i can advice you is avoid the **how to hack** resources at all most are just script kiddie stuff with no deep understand.
    - I advice you to just learn how computers work then ask yourself how can I break this, becoming a good hacker just takes time so have fun along the way.
    - anyways here are resources that I have looked at and found really helpfull
        - [hacker101](https://www.hacker101.com/)
        - [Liveoverflow](https://www.youtube.com/channel/UClcE-kVhqyiHCcjYwcpfj9w) say no more.
        
- **How can I hack Wifi?**
   - First learn how wifi works and wirelsess networks in general, then read about security vulnearbilities in network security protocols like WPA, WPA2 and WEP. 
   - The advantage with this method of learning even though it takes time in the end you will learn a lot about how computers work and know how to exploit them, even coming up with your own exploits.
   - Please dont google `how to hack ....`, dont be a [script kiddie/ skiddie](https://en.wikipedia.org/wiki/Script_kiddie)

## Any other random stuff.

**This are stuff that works for us, we may be wrong, apart from not being a skiddie!!**

- Dont be a [script kiddie/ skiddie](https://en.wikipedia.org/wiki/Script_kiddie)
- We think doing a lot of coding challenges helps make you a better coder, like [codewars](https://codewars.com/kata/) and [project euler](https://projecteuler.net/)
- Becoming an `expert` in most computer science fields takes time so you are better off enjoying the journey.
- Learning something by actually building it is a great way of learning, want to learn how the linux kernel works? well build your own. Check this repo out:[Build-your-own-x](https://github.com/danistefanovic/build-your-own-x)
- Maybe learning a low level language like C or Assembly helps understanding computers.

## Contributing 
- Incase theres anything you feel should be made clear or added to this documentation then dont hesitate to contact us.
- valid Pull requests are also welcomed.

## Contacts

Feel free to ask us questions. 

- Email: 
    - `ogina.jak@gmail.com` 
    - `xavier.kibet@gmail.com`
- Moringa School Slack Channel:
    - `@jack`
    - `@Xavier Kibet`
