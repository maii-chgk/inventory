# Inventory — what we own and how it works

## Website

[Our main website, maii.li](maii.li), lives in the [maii-site](https://github.com/maii-chgk/maii-site) repository. It’s deployed with Vercel, its CMS runs on Heroku. Forms use [Formspark](formspark.io) as their backend, file uploads in these forms work on [Uploadcare](https://uploadcare.com/).

## Membership and voting

### Forum

A [Discourse](https://www.discourse.org/) instance at [forum.znatoki.site](https://forum.znatoki.site/) runs on two DigitalOcean droplets (one for [its official Docker container](https://github.com/discourse/discourse_docker), one for its Postgres database). We use this forum for discussions and voting.

### Discord

We run a Discord server which is used as an Oauth provider for the forum. A subset of Discord server users are verified: that means that we have seen their IDs and checked that their Discord name is their real name.  

### Youtube channel

Assemblies are streamed to the [maii_info](https://www.youtube.com/@maii_info) Youtube channel.

### Register

[Register](https://github.com/maii-chgk/register) is a Rails application that we use to manage MAII membership. It runs on fly.io (on a single machine—it uses sqlite as its database). Register connects directly to the forum database (to add new members to a group and to fetch voting activity).


## Documents

### Google

Working groups and the executive committee use a shared Google Drive folder. Maxim Sidorov is the owner of this folder.

### Public documents

We maintain the history of all MAII documents in the [documents Github repository](https://github.com/maii-chgk/documents). [The statute page](https://www.maii.li/statute) on our website [is built using the file from that repository](https://github.com/maii-chgk/maii-site/blob/15c79de79e3dc4b03a6b12ee54a36e8824375e00/ui/_data/statute.js#L12).

## Email

We use a single [Fastmail](https://www.fastmail.com/) account for all email. Only an administrator has access to this account. All [working groups](https://www.maii.li/p/about#workgroups) receive an alias and provide a list of personal emails to which we redirect all emails sent to this alias.

## Rating

Everything rating-related ([importer](https://github.com/maii-chgk/rating-importer), [calculations](https://github.com/maii-chgk/rating-b), [website with results](https://github.com/maii-chgk/rating-ui), a shared Postgres database and a Redis instance for caching) runs on fly.io.

## Backups

### Amazon S3

Forum and register backups are uploaded to S3. The account is named MAII but is using Jury Razumau’s personal email.

## Cloudflare

Rating backups are uploaded to [Cloudflare R2](https://www.cloudflare.com/developer-platform/r2/).

## Domains

The maii.li domain name is managed through Jury Razumau’s personal Namecheap account.

## Services access

| Service      | How to get access                            |
|--------------|----------------------------------------------|
| Cloudflare   | Be a member of the MAII account              |
| DigitalOcean | Be a member of the MAII team                 |
| Fastmail     | Shared admin credentials                     |
| Fly.io       | Be a member of the MAII organisation         |
| Formspark    | Be a member of the workspace                 |
| Github       | Shared admin credentials                     |
| Github       | Be a member of the maii-chgk org             |
| Heroku       | Be a member of the MAII team                 |
| Uploadcare   | Shared admin credentials                     |
| Vercel       | Log in using the service MAII Github account |
| Youtube      | Shared admin credentials                     |
