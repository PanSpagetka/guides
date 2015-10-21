# Map of User Interface of ManageIQ
This file is used to document User Interface of ManageIQ

___


- [Cloud Inteligence](#cloud-inteligence)
- [Services](#services)
- [Clouds](#clouds)
- [Infrastructure](#infrastructure)
- [Containers](#containers)
- [Storage](#storage)
- [Control](#control)
- [Automate](#automate)
- [Optimize](#optimize)
- [Configure](#configure)

# Cloud Inteligence
## Dashboard
Index site of ManageIQ. Used to display widgets defined by user.

- Controller:

      dashboard_controller.rb

- Rendered Partials:

        layouts/_dhtmlx_tags.html.haml
        dashboard/_dropdownbar.html.haml
        dashboard/_widget_blank.html.haml
        dashboard/_widget_footer.html.haml
        dashboard/_widget.html.haml
        dashboard/_widget_chart.html.haml
        dashboard/_widget_report.html.haml
        dashboard/show.html.haml
        layouts/_doctype.html.haml
        stylesheets/_template50.html.haml
        layouts/_user_options.html.haml
        layouts/_page_header_navbar.html.haml
        layouts/_spinner.html.haml
        layouts/_lightbox_panel.html.haml
        layouts/_header.html.haml
        layouts/_tabs.html.haml
        layouts/_content.html.haml
        layouts/_adv_search.html.haml
        layouts/_footer.html.haml

## Reports

- Controler:

      report_controller.rb

### Saved Reports
- Tree:
   - All Saved Reports
      - Configuration
        - Group of Reports
          - Configuration
            - Report

    - All Saved Reports
      - Configuration(Delete selected saved Reports(disabled))
        - Group of Reports
          - Main Div:
            - Displays Table with all Saved Reports

    Configuration(Delete selected saved Reports(disabled))

- Rendered partials:

        layouts/_info_msg.html.haml
        layouts/_flash_msg.html.haml
        layouts/gtl/_list.html.haml
        layouts/_x_gtl.html.haml
        report/_savedreports_list.html.haml
        layouts/_x_form_buttons.html.haml
        layouts/_x_pagingcontrols.html.haml



- Report<br>
  Configuration(Show full screen report, Delete this Reports form the Database)
  Main Div:
      Displays Table with all Saved Reports<br>

- Rendered partials:

        layouts/_info_msg.html.haml
        layouts/_flash_msg.html.haml
        layouts/gtl/_list.html.haml
        layouts/_x_gtl.html.haml
        report/_savedreports_list.html.haml
        layouts/_x_form_buttons.html.haml
        layouts/_x_pagingcontrols.html.haml

### Reports
- Tree:
    - All Reports
      - Folder
        - Subfolder
          - Report

    - All Reports
      - Configuration(Add a new Report)
        - Folder
         - Configuration(Add a new Report)
            - Subfolder
              - Configuration(Add a new Report)
                - Report
                  - Queue()
                    - Configuration(Add a new Report, Copy this Report, Add a new Schedule)

### Schedules
      - All Schedules
            - Schedule
### Dashboards
      - All Dashboards
            - Default Dashboard
            - All Groups
                  - Group
                        - Dashboard
### Dashboard Widgets
### Edit Reports Menus
### Import/Export
## Chargeback
## Timelines
## RSS

___

# Services
## My Services
## Catalogs
## Workloads
## Requests

___

# Clouds
## Providers
## Availability Zones
## Tenants
## Flavors
## Security Group
## Instances
## Stacks

___

# Infrastructure
## Providers
## Clusters
## Hosts
## Virtual Machines
## Resource Pools
## Datastores
## PXE
## Requests
## Configuration Management

___

# Containers _(default hidden)_
TODO: Tab can be displayed by adding `containers:true` into production.yml in Configuration page
## Providers
## Projects
## Container Nodes
## Pods
## Routes
## Replicators
## Container Services
## Containers
## Image Regstries
## Topology

___

# Storage _(default hidden)_
TODO: Tab can be displayed by adding `analytics:true` into production.yml in Configuration page
## Filters
## Volumes
## LUNs
## File Shares
## Storage Managers

___

# Control
## Explorer
## Simulation
## Import / Export
## Log

___

# Automate
## Explorer
## Simulation
## Customization
## Import / Export
## Log
## Requests

___

# Optimize
## Utilization
## Planning
## Bootlenecks

___

# Configure
## My Settings
## Tasks
## Configuration
## About
