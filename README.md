# AC-Toolbox
_ActiveCollab Toolbox_

## Motivation

My client is using the Cloud Service "ActiveCollab" for in their group to manage project, tasks and communications inside of the group but also with external partners.  ActiveCollab is essential for this Company.

They trust in Cloud Services but it would be foolish to blindly trust it will be always there.

There are some risks, like the Company behind AC will get bankrupt or the system gets hacked or the data center burns down etc.

Other requirement is by partners.  They need, by law, need backups of their whole communication what is stored inside AC.

Therefore some actions need to be taken to cover these risks.


## License

I am not an employee of [ActiveCollab Inc.](https://activecollab.com) and I have no business with them.

The ActiveCollab Software is copyright and owned by ActiveCollab Inc. and you need a license to be allowed to run the self-hosted software.  Get it from there https://activecollab.com/self-hosted-project-management

This **AC-Toolbox** is Open-Source and free to use, but use it at your own risk.  I can not, and will not, guarantee everything is working for your needs.


## Solution

I build a Toolbox around ActiveCollab to 

- be able to run ActiveCollab on a self-hosted server using Docker
- backup the data to local server
- import the backup to the self-hosted AC
- export an extract of the backup files to our partners (as static HTML Files)
- provide a download service to securely fetch the backups

![](./Assets/ActiveCollab%20Toolbox%20Overview.png)

There will be the following GIT Reposities

- `ac-docker` - a Docker based setup to run self-hosted ActiveCollab (does not contain AC itself because of licensening!)
- `ac-py-api` - an AC Client API written in Python 
- `ac-backup` - some Python scripts, using the `ac-py-api` to dump data from AC into JSON files
- `ac-to-html` - generate static HTML files from `ac-backup` JSON files
- `ac-backup-provider` - a web-based download server provide the static HTML files, including the related JSON files and attachments, used by the partners to download backup files

## Safety Warning!

Because the toolbox need access to your Production ActiveCollab Instance you should create an own user account and give only the permissions to the projects you want or need to backup.  The User should not have the rights to modify or delete data on your Production System.

> Be careful!


## Support for Setup & Changes

If you want to setup the AC-Toolbox but need help, you can contact me.

The current version of the backup does not backup all data, we only save the parts my client needs.  If you want to extend the software you can consult me.

From time to time the Cloud-API is changing and then the backup scripts may break and stop working.  I will take account of these changes timely, and publish the changes as soon as possible.  Therefore this AC-Toolbox is Open-Source so you could do the required changes by yourself or hire someone to do it.



