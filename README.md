# Gaderian

A tool to gather your data locally in one place and allow you to explore it.

## Mission

Many companies hold your data. Often you use apps to view your data or recieve emails with data attached.

With policies like GDPR it is possible to request a company give you a copy of all of the data they hold on you, and to delete you from their system entirely. The problem with this is that the data they provide is often unwieldy to manage. Also in many cases you probably want them to have data on you in order to provide you a service. 

The aim of Gaderian is as follows:

- Continuously gather your data locally onto a storage medium which is easy to use and access.
- Provide tools to explore your own data.
- Consolidate information on how to request data deletion or a full download from various companies. 

## How?

To achieve this goal I propose creating an application which stored data from many sources (extensible by contributors) and stores that data locally. This application would be run on a device like a Raspberry Pi with an attached external hard drive. It should be possible for users to explore the data locally via a web app or native app. It should also be possible for users to disconnect the hard drive, connect it to any computer and explore the data using tools of their choice, such as excel.

I currently see this project taking two parts:

- A locally hosted JAMStack-ish application with the backend service and API written in Python and frontend written in JavaScript (maybe React)
  - This service may depend on other services like an SQL server, document storage and/or timeseries database
  - All data stored in various databases should also be stored as flat files on an external hard drive
- A Raspberry Pi OS image with the application and dependencies installed and configured

## Use cases

### Fitness devices

Fitness devices are very popular to track steps, exetercise, sleep and more. The data that these devices collect are often uploaded to the manufacturer of the device who likely also provides an app to allow you to view the data. 

Some apps also integrate with aggregation services like [Apple's Health](https://developer.apple.com/health-fitness/) app which shows you a view on all the data collected by the various health related apps you use. While aggregating this data is useful it is still possessed by others who are making it available to you, and not you yourself.

In this case Gaderian would gather fitness data, have a health style visualisation tool and also archive data to CSVs on a hard drive.

### Utility bills

Many home utility providers such as heating, electricity and telecoms have important data such as usage and bills which you should be keeping an eye on regularly.

Over the last few years many providers have been making the move away from paper statements and invoices to online portals. Sadly many of which are poor quality, slow and hard to use. This tends to make it harder to heep track of these things.

Gaderian would download and archive PDF documentes anbd provide rich search utilities.
