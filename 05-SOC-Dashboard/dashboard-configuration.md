# Custom SOC Activity Dashboard

## Dashboard name

**Tushar Tyagi SOC Activity Overview**

## Panels visible in the dashboard

  --------------------------------------------------------------------------------
  Panel                                        What it displays
  -------------------------------------------- -----------------------------------
  `failed window logon`                        Count of failed Windows logon
                                               events

  `Window Account Changes Over Time`           Time-series view of Windows
                                               account-related event IDs

  `Linux Failed SSH Authentication Activity`   Table of Linux SSH failure
                                               activity, agent, timestamp,
                                               source-user field, and count
  --------------------------------------------------------------------------------

## Screenshot observations

The dashboard screenshot shows: - Failed Windows logon count: `4` -
Windows account event trend with multiple event IDs in the legend. -
Linux SSH activity table containing agent `tushar-Linux` and event
counts.

These counts are a snapshot for the selected dashboard time range, not
permanent totals.

## Analyst use

The dashboard provides a quick triage overview. It does not
independently determine whether an event is malicious. The analyst
should open the underlying event and inspect its details.

## Evidence

-   `../09-Evidence/07-soc-dashboard.png`
