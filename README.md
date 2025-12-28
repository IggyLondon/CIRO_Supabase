# CIRO Supabase Keep-Alive

This repository contains a GitHub Actions workflow that automatically keeps your Supabase project active by pinging the database every 5 days.

## Purpose

Supabase free-tier projects pause after 7 days of inactivity. This workflow prevents that by making a lightweight API request to your `gallery_images` table every 5 days.

## How It Works

- **Automatic Schedule**: Runs every 5 days at 12:00 UTC
- **Direct Database Query**: Makes a simple request to fetch one record from the `gallery_images` table
- **Manual Trigger**: Can also be triggered manually from the GitHub Actions tab

## Workflow Details

The workflow file is located at `.github/workflows/supabase-keepalive.yml`

It queries: `https://emnuwkxroirerhbablfr.supabase.co/rest/v1/gallery_images?select=id&limit=1`

## Monitoring

You can monitor the workflow runs by going to the **Actions** tab in this repository. Each run will show:
- When it ran
- Whether it was successful
- Logs of the API request

## Security

The workflow uses your Supabase public `anon` key, which is designed to be used in client-side applications and is safe to include in public repositories.

---

Created with Manus AI to solve the Supabase free-tier inactivity pause issue.
