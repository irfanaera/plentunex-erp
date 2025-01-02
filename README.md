[![Build Status](https://runbot.odoo.com/runbot/badge/flat/1/master.svg)](https://runbot.odoo.com/runbot)
[![Tech Doc](https://img.shields.io/badge/master-docs-875A7B.svg?style=flat&colorA=8F8F8F)](https://www.odoo.com/documentation/master)
[![Help](https://img.shields.io/badge/master-help-875A7B.svg?style=flat&colorA=8F8F8F)](https://www.odoo.com/forum/help-1)
[![Nightly Builds](https://img.shields.io/badge/master-nightly-875A7B.svg?style=flat&colorA=8F8F8F)](https://nightly.odoo.com/)

Odoo
----

Odoo is a suite of web based open source business apps.

The main Odoo Apps include an <a href="https://www.odoo.com/page/crm">Open Source CRM</a>,
<a href="https://www.odoo.com/app/website">Website Builder</a>,
<a href="https://www.odoo.com/app/ecommerce">eCommerce</a>,
<a href="https://www.odoo.com/app/inventory">Warehouse Management</a>,
<a href="https://www.odoo.com/app/project">Project Management</a>,
<a href="https://www.odoo.com/app/accounting">Billing &amp; Accounting</a>,
<a href="https://www.odoo.com/app/point-of-sale-shop">Point of Sale</a>,
<a href="https://www.odoo.com/app/employees">Human Resources</a>,
<a href="https://www.odoo.com/app/social-marketing">Marketing</a>,
<a href="https://www.odoo.com/app/manufacturing">Manufacturing</a>,
<a href="https://www.odoo.com/">...</a>

Odoo Apps can be used as stand-alone applications, but they also integrate seamlessly so you get
a full-featured <a href="https://www.odoo.com">Open Source ERP</a> when you install several Apps.

Getting started with Odoo
-------------------------

For a standard installation please follow the <a href="https://www.odoo.com/documentation/master/administration/install/install.html">Setup instructions</a>
from the documentation.

To learn the software, we recommend the <a href="https://www.odoo.com/slides">Odoo eLearning</a>, or <a href="https://www.odoo.com/page/scale-up-business-game">Scale-up</a>, the <a href="https://www.odoo.com/page/scale-up-business-game">business game</a>. Developers can start with <a href="https://www.odoo.com/documentation/master/developer/howtos.html">the developer tutorials</a>

Odoo Setup :
1. git clone https://github.com/odoo/odoo.git (version 18)
2. Download and install python 3.10 then add python folder to path environment
3. Download and install PostgreSQL 17 then add PostgreSQL bin folder to path environment
4. python -m pip install --upgrade pip
5. pip install setuptools wheel
6. pip install -r requirements.txt
7. Download and install https://github.com/wkhtmltopdf/packaging/releases/download/0.12.6-1/wkhtmltox-0.12.6-1.msvc2015-win64.exe then add wkhtmltopdf bin folder to path environment
8. python odoo-bin -i account,account_debit_note,crm,sales_management,web_site,stock,purchase,point_of_sales,project,mrp,mass_mailing,hr,hr_expense,hr_holidays,hr_recruitment,data_recycle,maintenance,website_event,calendar,contacts,im_livechat,repair,hr_attendance,mass_mailing_sms,project_todo,hr_skills,hr_contract,website_google_map,website_blog,website_crm_partner_assign,website_customer,mail_plugin,crm_mail_plugin,project_mail_plugin,auth_oauth,base_geolocalize,base_automation,hr_homeworking,marketing_card,survey
9. Theme Setup :
	a. Import module https://apps.odoo.com/apps/modules/18.0/theme_common
	b. Import module https://apps.odoo.com/apps/themes/18.0/theme_clean

Uninstall Module:
1. python odoo-bin shell
2. self.env['ir.module.module'].search([('name','=','muk_web_theme')]).button_immediate_uninstall()
3. exit()


Create DB
createdb -U postgres iplus_erp

Backup Db
pg_dump --username=postgres --dbname=iplus_erp_backup --file=C:\Irfan\Projects\IPlus\iplus_erp\odoo_backup.sql --table=hr_* --inserts --column-inserts
pg_dump --username=postgres --dbname=iplus_erp --file=C:\Irfan\Projects\IPlus\iplus_erp\iplus_erp_01-Jan-2025.backup --format=t
pg_dump -U postgres -d iplus_erp -f C:\Irfan\Projects\IPlus\iplus_erp\iplus_erp_v1_02-Jan-2025.backup -F t

Drop DB
dropdb --username=postgres iplus_erp

Restore DB
pg_restore --username=postgres --dbname=iplus_erp -1 C:\Irfan\Projects\IPlus\iplus_erp\iplus_erp_initial_01-Jan-2025.backup