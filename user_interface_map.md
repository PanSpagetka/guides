<script type="text/javascript" src="//ajax.googleapis.com/ajax/libs/jquery/1/jquery.min.js"></script>
# Map of User Interface of ManageIQ
This file is used to document User Interface of ManageIQ

#Cloud Inteligence
###Dashboard
####Description:
Index site of ManageIQ.
####Rendered Partials:

###Reports

####Saved Reports
######Controler:
report_controller.rb

######Tree:
- All Saved Reports
  Configuration
  - Group of Reports
    Configuration
    - Report

- All Saved Reports<br>
  Configuration(Delete selected saved Reports(disabled))
  - Group of Reports<br>
    Main Div:<br>
    Displays Table with all Saved Reports<br>


    Rendered partials:<br>
    layouts/_info_msg.html.haml
    layouts/_flash_msg.html.haml
    layouts/gtl/_list.html.haml
    layouts/_x_gtl.html.haml
    report/_savedreports_list.html.haml
    layouts/_x_form_buttons.html.haml
    layouts/_x_pagingcontrols.html.haml
    Configuration(Delete selected saved Reports(disabled))


    - Report<br>
      Configuration(Show full screen report, Delete this Reports form the Database)
      Main Div:<br>
      Displays Table with all Saved Reports<br>
      Rendered partials:<br>
        layouts/_info_msg.html.haml<br>
        layouts/_flash_msg.html.haml<br>
        layouts/gtl/_list.html.haml<br>
        layouts/_x_gtl.html.haml <br>
        report/_savedreports_list.html.haml <br>
        layouts/_x_form_buttons.html.haml<br>
        layouts/_x_pagingcontrols.html.haml<br>

####Reports
######Tree:
- All Reports
  - Folder
    - Subfolder
      - Report

- All Reports<br>
  Configuration(Add a new Report)<br>
  - Folder<br>
    Configuration(Add a new Report)
    - Subfolder<br>
      Configuration(Add a new Report)
      - Report<br>
        Queue()<br>
        Configuration(Add a new Report, Copy this Report, Add a new Schedule)

####Schedules
####Dashboards
####Dashboard Widgets
####Edit Reports Menus
####Import/Export

###Chargeback

###Timelines

###RSS

#Services
###My Services
###Catalogs
###Workloads
###Requests

#Clouds
###Providers
###Availability Zones
###Tenants
###Flavors
###Security Group
###Instances
###Stacks

#Infrastructure
###Providers
###Clusters
###Hosts
###Virtual Machines
###Resource Pools
###Datastores
###PXE
###Requests
###Configuration Management

#Containers(default hidden)
###Providers
###Projects
###Container Nodes
###Pods
###Routes
###Replicators
###Container Services
###Containers
###Image Regstries
###Topology

#Control
###Explorer
###Simulation
###Import / Export
###Log

#Automate
###Explorer
###Simulation
###Customization
###Import / Export
###Log
###Requests

#Optimize
###Utilization
###Planning
###Bootlenecks

#Configure
###My Settings
###Tasks
###Configuration
###About
