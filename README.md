##### [Home repo](https://github.com/overwasher/home/) | [Overwatcher code](https://github.com/overwasher/overwatcher) | [Sensor Node code](https://github.com/overwasher/esp-firmware) | [Telegram bot code](https://github.com/overwasher/telegram-bot) | [Task Tracker](https://taiga.dcnick3.me/project/overwasher/)

# Overwasher

## Table of contents

* [What is it?](#what-is-it-)
  + [Motivation](#motivation)
  + [Goals](#goals)
  + [Are there any competitors?](#are-there-any-competitors-)
* [Glossary](#glossary)
* [Architecture](#architecture)
  + [Important constraints and limitations](#important-constraints-and-limitations)
  + [Tradeoff decisions](#tradeoff-decisions)
* [How to contribute](#how-to-contribute)
* [Creators](#creators)

## What is it?

It is a student project that allows people to find out which closest washing machine or drying machine is currently free to use in campus. 

It involves:

Sensor nodes that collect data and status of washing/drying machines

An overwatcher microservice to aggregate data from sensor nodes

A telegram bot to communicate with users

### Motivation

There are many students on campus and it is hard to know where to go if you want to wash your clothes as any of washing machines may be busy. Moreover, if you decide to dry your clothes afterwards, you never know when drying is going to finish.

But fear not, the cavalry is here!

We will track which washing machines and dryers are in use using fancy sensors (tm) and advanced machine learning (c) techniques and provide you with this information via a telegram bot!

### Goals

### Are there any competitors?

There are no well-known competitors. Even worse, there are no competitors who would create something easy-to-build and easy-to-scale. What is more, nobody has done so on Innopolis University campus! So this project is quite unique.

## Glossary

* Sensor node -- aggregate of hardware and software solutions that collects data and status of washing and drying machines and sends data to Overwatcher

* Overwatcher -- software micro service that collects data from all sensor nodes via the protocol and gives nice API to telegram bot

* Telegram bot -- a bot for Telegram that uses Overwatcher API to direct users to best washing/drying machine

* Free washing/drying machine is a machine that is functional and is not actively washing or drying at the moment

* Not working or broken washing/drying machine is a machine that is unable to function

## Architecture

### Important constraints and limitations

### Tradeoff decisions 

During development there were some important tradeoff decisions that affected the design in the end.

If you are interested in why we use ESP32 and not ESP8266 and in some other important desisions that affected the development feel free to visit our [Task Tracker](https://taiga.dcnick3.me/project/overwasher/)

## How to contribute

Currently, the project is in heavy development and may change a lot in the nearest future. 

*We do not recommend contributing at this stage*. 

Later, when project becomes more stable, we may create some contribution guidelines for everyone to use. 

## Creators

- Nikita Strygin 
- Violetta Sim
- Vyacheslav Sergeev
