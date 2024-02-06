# Tag Manager Folder Contents
- PDFs
- Video Tutorial Links
- Json Template Files

## Video Tutorials
[Setting up Google Analytics 4](https://cdn.treehouseinternetgroup.com/cms_images/687/01-Setup-GA4.mp4)

[Setting up Google Tag Manager](https://cdn.treehouseinternetgroup.com/cms_images/687/02-Setup-GTM-Portal.mp4)

[Setting up Measurement ID Data Variable](https://cdn.treehouseinternetgroup.com/cms_images/687/03-Setup-Measurement-ID.mp4)

[Setting up Configuration Tag (GTM)](https://cdn.treehouseinternetgroup.com/cms_images/687/04-Setup-Config-Tag.mp4)

[Setting up Lead Conversion Event](https://cdn.treehouseinternetgroup.com/cms_images/687/05-Setup-Leads-Event.mp4)

## Shortcut: Importing Json Template File
1. Download the appropriate Json file for whichever domain is being set up. [HG = HelloGarage]
2. Navigate to **Google Tag Manager -> Admin -> Import Container**
3. Select the Json file as the **Select file to import**.
4. Choose **Existing** as your Workspace.
5. Select **Merge** as your import option. There *should* be no conflicts but in the rare case that there is, you can rename whatever tags, triggers or variables as needed.
6. Click **Confirm** and check the workspace to ensure everything was imported correctly.
7. Once the container is imported, go to **Variables -> User-Defined Variables -> Measurement ID** and replace the **Value** with the appropriate Measurement ID in GA4. Please refer to [this video](https://cdn.treehouseinternetgroup.com/cms_images/687/03-Setup-Measurement-ID.mp4) if you need help finding the Measurement ID in GA4.
