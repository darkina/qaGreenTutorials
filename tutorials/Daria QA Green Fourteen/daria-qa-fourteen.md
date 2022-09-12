---
title: Daria QA Green Fourteen changed
description: Build and deploy a multi-target application (MTA) project in SAP Web IDE, generate a test notification in SAP IoT, and launch the decision support application.
author_name: Jitendra Sharma
author_profile: https://github.com/JitendraSharma01
auto_validation: true
time: 20
primary_tag: topic>internet-of-things
tags: [ tutorial>community, tutorial>beginner, tutorial>license, topic>internet-of-things, topic>cloud, products>sap-internet-of-things, products>sap-business-technology-platform, products>sap-web-ide ]
---

## Details
### You will learn
  - How to build and deploy an MTA project
  - How to test SAP IoT notification
  - How to test decision support application

If you make any changes to an MTA project, you'll need to build and deploy the project for the changes to take effect.

---

[ACCORDION-BEGIN [Step 1: ](Build MTA project)]

  1. In SAP Web IDE, right click the iot-ds project and click **Build** to start the build of the project.

    ![Initiate project build](/images/shared/webide_build_0_1.png)

  2. When the build is completed, a notification will be displayed at the top right corner of the SAP Web IDE.  

  3. You can also check the status of the build by viewing the logs in the SAP Web IDE console.

    ![Project is built successfully](/images/shared/webide_build_1.png)  

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 2: ](Deploy MTA project)]

  1. You need to have the following entitlements in your Cloud Foundry sub-account to **deploy** and **run** our application.  You can find more information on how to configure entitlements in [Configure entitlements and Quotas for Subaccounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5ba357b4fa1e4de4b9fcc4ae771609da.html).

    Entitlement | Unit
    ------------ | -------------
    Portal|1 (or unlimited)
    Application Runtime Memory| 1 Gib (Minimum)
    Destination|1

  2. To start a deployment, expand the `mta_archives` folder in your project, right click the `mtar` file inside the folder and click **Deploy to SAP Business Technology Platform**.

    ![Deploy project to SAP BTP](/images/shared/webide_build_3_btp.png)

  3. Select the appropriate **Cloud Foundry API Endpoint**, **Organization** and **Space** for your deployment.  If you cannot find your selections, please check your Cloud Foundry settings in SAP Web IDE preference.

  4. Click **Deploy**.

    ![Enter SAP BTP information](/images/shared/webide_build_4.png)

  5. When the deployment is completed, a notification will be displayed at the top right corner of the SAP Web IDE.

  6. You can also check the status of the deployment by viewing the logs in the SAP Web IDE console.

    ![Project is deployed successfully](/images/shared/webide_build_5.png)  

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 3: ](Retrieve thing id)]

  You will need to retrieve the thing id for the next step. If you already have the thing id, please proceed to the next step.

  1. From SAP IoT launchpad, select the **Thing Modeler** tile.

    ![Select Thing Modeler in SAP Fiori launchpad](/images/shared/thing_modeler_tile.png)  

  2. Select the `greenhouse` package and select **Things** on the left panel.

  3. Click the **Connectivity Information** icon on the top right corner.

    ![Select greenhouse package and click connectivity information](/images/shared/thing_modeler_1.png)  

  4. Copy the thing id.  You'll use it in the next step.

    ![Copy thing id](/images/shared/thing_id.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 4: ](Generate test notification)]

  1. From SAP IoT launchpad, select the **Actions** tile.

    ![Select actions from SAP Fiori launchpad](/images/shared/launchpad_tile_actions_1.png)

  2. Select **Greenhouse Action**.

    ![Select greenhouse action](/images/shared/test_portal_1_2.png)

  3. Click **Test**.

    ![Click Test](/images/shared/test_portal_2_1.png)

  4. Enter the **Thing Id** in the **Test Action** dialog. Click **Test**.

    ![Enter thing id and click Test](/images/shared/test_portal_3_1.png)


[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 5: ](Check notification in launchpad site)]

  1. To find the URL of the SAP Fiori launchpad site, go to the SAP BTP Cockpit, navigate to the space of the sub-account where the MTA project is deployed.

  2. Navigate to the **Applications** screen.

  3. Click `iot-ds_appRouter`.

    ![Find deployed application in SAP BTP cockpit](/images/shared/find_portal_url_1_btp2.png)

  4. You should see the route displayed under **Application Routes**.

    ![Find application route](/images/shared/find_portal_url_2_btp2.png)

  5. Click on route to launch SAP Fiori launchpad site.

  6. Launch the SAP Fiori launchpad site in a browser.  You should see a SAP Fiori notification alert.

    ![Notification alert displayed in SAP Fiori launchpad](/images/shared/test_notif_1_1.png)

  7. Click the alert icon and the SAP Fiori notification panel will be opened.

    ![Open notification](/images/shared/test_notif_2_1.png)

[DONE]
[ACCORDION-END]
