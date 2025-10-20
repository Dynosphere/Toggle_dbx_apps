# Toggle_dbx_apps
Simple toggle for databricks apps

# What and why?

Until scale to zero is available for Databricks apps, some people want to toggle an app on or off before they start.
This repo contains:
- **executed as job** A notebook which is paramterised to toggle any app given an `app_id` between a `day_start_hour` and a `day_end_hour` using the Databricks SDK.
- **Executed interactive** A bundle generator which has three purposes:
  - Provide the user entry for configs (which apps, when)
  - To iteratively generate a job configuration,
  - updates resources/pipelines.yml for you to add / remove tasks from your deployment.
- A asset bundle and relevant config to deploy your app control job.


# How do i use it?

In the DBX UI:
- Clone this repository
- Edit `utils/bundle_generator` cell 3: Update me with your details.
- Click on the deployments icon on the left hand side bar (Little rocket), deploy to dev

You should have a new job deployed in your workspace. This won't do anything unless you run it.

For running on a schedule, you need to update cell 4, line 18 in `utils/bundle_generator` with your schedule, and then update `databricks.yml` with a non-dev target.

# Disclaimer
This code is not endorsed by or affiliated in any way with Databricks. Use it at your own risk and review everything before using it.