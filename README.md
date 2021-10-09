##### [Home repo](https://github.com/overwasher/home/) | [Overwatcher code](https://github.com/overwasher/overwatcher) | [Sensor Node code](https://github.com/overwasher/esp-firmware) | [Telegram bot code](https://github.com/overwasher/telegram-bot) | [Task Tracker](https://taiga.dcnick3.me/project/overwasher/)

# Overwasher

Overwasher allows people to find out which washing or drying machine is currently free to use on campus.

## Table of contents

* [Features](#features)
  + [Motivation](#motivation)
  + [Goals](#goals)
  + [Are there any competitors?](#are-there-any-competitors)
* [Glossary](#glossary)
* [Architecture](#architecture)
  + [Overview](#overview)
  + [Tradeoff decisions](#tradeoff-decisions)
* [How to contribute](#how-to-contribute)
* [Creators](#creators)

## Features

- Sensor nodes that statuses of washing/drying machines
- An overwatcher microservice to aggregate data from sensor nodes
- A telegram bot to communicate with users

### Motivation

There are many students on campus and it is hard to know where to go if you want to wash your clothes as any of washing machines may be busy. Moreover, if you decide to dry your clothes afterwards, you never know when drying is going to finish.

But fear not, the cavalry is here!

We will track which washing machines and dryers are in use using fancy sensors (tm) and advanced machine learning (c) techniques and provide you with this information via a telegram bot!

### Goals

- Provide user with relatively up-to-date information on washing and drying mashines statuses
- Make all the hardware non-invasive: we don't want any warranties voided or critical devices broken
- Minimize the amount of required maintenance: after the development phase the system should not require much labour to support

### Are there any competitors?

There are no well-known competitors. Even worse, there are no competitors who would create something easy-to-build and easy-to-scale. What is more, nobody has done so on Innopolis University campus! So this project is quite unique.

## Glossary

* Sensor node — aggregate of hardware and software solutions that collects data and status of washing and drying machines and sends data to Overwatcher

  * PCB — printed circuit board that is the hardware for Sensor node

  * Telemetry — raw values from accelerometer that are collected and used for later analysis 

  * TM — telemetry manager, module of sensor node that curates collection and sending telemetry

  * Activity — status of machine at some point in time (active — busy washing or drying)

  * AD — activity detection, module of sensor node that processes the data from accelerometer to judge whether machine is active or not

* Overwatcher — software micro service that collects data from all sensor nodes via the protocol and gives nice API to telegram bot

* Telegram bot — a bot for Telegram that uses Overwatcher API to direct users to best washing/drying machine

* Free washing/drying machine is a machine that is functional and is not actively washing or drying at the moment

* Not working or broken washing/drying machine is a machine that is unable to function

## Architecture

### Overview

Our architecture contains 3 microservice types that interact via APIs.

Only telegram bot is user-facing, it masks the complex hardware and software design that is happening to deliver machines' status

![](https://files.catbox.moe/7g8v3o.jpg)

Note, that we have two independent control flows:

* Sensor nodes send activity and telemetry to overwatcher whenever they feel like it.

* When user interacts with the telegram bot, bot requests the most fresh data from overwatcher

### Tradeoff decisions 

During development there were some important tradeoff decisions that affected the design in the end.

If you are interested in why we use ESP32 and not ESP8266 and in some other important desisions that affected the development feel free to visit our [Task Tracker](https://taiga.dcnick3.me/project/overwasher/wiki/tradeoff-decisions-about-quality)

## How to contribute

Currently, the project is in heavy development and may change a lot in the nearest future. 

*We do not recommend contributing at this stage*. 

Later, when project becomes more stable, we may create some contribution guidelines for everyone to use. 

## Creators

- Nikita Strygin
  * Telegram: [@DCNick3](https://t.me/DCNick3)
  * Github: [@DCNick3](https://github.com/DCNick3)
- Violetta Sim
  * Telegram: [@eyihluyc](https://t.me/eyihluyc)
  * Github: [@eyihluyc](https://github.com/eyihluyc)
- Vyacheslav Sergeev
  * Telegram: [@unb0und](https://t.me/unb0und)
  * Github: [@HisMaj3sty](https://github.com/HisMaj3sty)

## Licence

All repositories in Overwasher codebase are licenced under GNU Affero General Public License v3.0
