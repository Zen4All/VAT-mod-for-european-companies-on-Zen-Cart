# VAT-mod-for-european-companies-on-Zen-Cart

<h2>!! This code has not been tested yet. Do not use in a live store !!</h2>This mod checks customer's VAT (Value Added Tax) number regarding his country and displays VAT on invoice and packingslip as well as removes tax when shipping to companies in countries within the EU.

This mod checks customer's VAT (Value Added Tax) number regarding his country and displays VAT on invoice and packingslip as well as removes tax when shipping to companies in countries within the EU.
- Add a text field during account registration and modification...
- Add shop VAT number on invoice and packing slip
- Add customer VAT number on invoice
- Removes tax in checkout (if configured correctly) if customer has entered VAT number and is in a country within EU but is in a country other than the Store.
- Check VAT number for registering companies (if implemented in admin) according to their country.
- Control of the VAT number is done in admin (for both customers and shop number)
- Enable/disable server verification in configuration (in admin). 


VAT-Mod BETA UNOFFICIAL for Zen Cart v. 1.3.9h
For Companies inside European Union
===========================
Remake and compatibility with Zen Cart v. 1.3.9h
Special edition done by dimjoula.

Mod by Sebastian Bergquist/Beez (http://www.sweetfabrik.se) & Viktor Bergquist/vike
http://www.zen-cart.com/forum/showthread.php?p=201772


IMPORTANT NOTE: THIS IS NOT THE OFFICIAL RELEASE FROM Beez & Vike. 
IT IS A *BETA* VERSION. I DID A COPY AND PASTE FROM THE PREVIOUS CODES (VAT-Mod 1.3.0 for Zen Cart v. 1.3.8a) AND PASTE IT TO Zen Cart v. 1.3.9h FILES. IT WORKS FOR ME WITH MY OWN PERSONAL CONFIGURATION, BUT YOU SHOULD TAKE IT WITH CARE. IT MAY NOT WORK WITH YOUR OWN CONFIGURATION.

BACKUP - BACKUP first your files and database before updating your store with these files. It may be buggy. You must know how to restore it!!!

What's new:
- PARTIAL (90%) Compatibility with Zen Cart v. 1.3.9h (but should be OK in most regular situations; potential problem when the customer uses several different addresses located in different countries)
- french translation
- update of the VIES link to check the validity of the number (only for a compatibility with php 5.3)
- THIS FUNCTION INTRODUCED IN THE PREVIOUS MOD DOES NOT WORK ANYMORE: "Don't add tax on any prices in the store if customer is logged in with verified VAT-number and customers shipping address is not in the same country as the store." So, the file catalog/includes/functions/functions_taxes.php is not updated. Please, use the geniune file from 1.3.9h instead.



----------------------------------------------
Compatibility zen-cart-v1.2.2d. 
Hack by Jean Gourdon, Paris France.
http://www.zen-cart.com/forum/showthread.php?t=9620
----------------------------------------------
Original work:
VAT legal & INTRACOM V3.93 - Gyakutsuki / JeanLuc - Under GPL
Credit goes to the author !
http://www.oscommerce-fr.info/forum/index.php?showtopic=9507
===========================
What does this mod do?
This mod checks customer's VAT number regarding his country and displays VAT on invoice and packingslip as well as removes tax when shipping to companies in countries within the EU.

- Add a text field during account registration and  modification...
- Add shop VAT number on invoice and packing slip
- Add customer VAT number on invoice
- Don't add tax in checkout payment (if configured correctly) if customer has entered VAT number and is in a country within EU but is in a country other than the Store.

- Control of the VAT number is done in admin (for both customers and shop number)
- Enable/disable server verification in configuration (in admin).
- Check VAT number for registering companies (not yet implemented in admin) according to their country.
----------------------------------------------
Limitations and future releases

----------------------------------------------
PLEASE BACK UP, then BACK UP & finally BACK UP YOUR WORK BEFORE ANY MODIFICATIONS !!!
===========================
The figure of the VAT number (10 minimum) can be set in: Admin/Configuration/VAT
For info:
Germany			DE + 9 numeric characters 
Austria			AT + 9 numeric and alphanumeric characters 
Belgium			BE + 10 numeric characters
Bulgaria		BG + 9 or 10 numeric characters
Cyprus 			CY + 8 numeric characters + 1 alphabetic character  
Czech Republic 		CZ + 8 or 9 or 10 numeric characters 
Denmark			DK + 8 numeric characters 
Estonia			EE + 9 numeric characters 
Finland			FI + 8 numeric characters 
France			FR + 2 chiffres (informatic key) + N¡ SIREN (9 figures) 
Germany			DE + 9 numeric characters 
Greece			EL + 9 numeric characters 
Hungary			HU + 8 numeric characters 
Irlande			IE + 8 numeric and alphabetic characters 
Italy			IT + 11 numeric characters 
Latvia 			LV + 11 numeric characterss 
Lithuania 		LT + 9 or 12 numeric characters 
Luxembourg		LU + 8 numeric characters 
Malta 			MT + 8 numeric characters 
Netherlands		NL + 12 alphanumeric characters, one of them a letter 
Poland	 		PL + 10 numeric characters 
Portugal		PT + 9 numeric characters 
Romania			RO + 2 to 9 numeric characters
Spain 			ES + 9 characters 
Sweden 			SE + 12 numeric characters 
Slovakia  		SK + 9 or 10 numeric characters 
Slovenia		SI + 8 numeric characters
United Kingdom		GB + 9 numeric characters 
===========================
A. Database

In you database
Please use the file VAT-mod_English.sql in order to update your database. You can use the "Install SQL Patches" under Tools in the Admin-area.

===========================
B. Files
1. About folders & files to be modified

If you are using a new zencart 1.3.8a version without any modifications you may be able to replace the following files in your installation with the new ones provided in this contribution. Don't forget other language files.
===========================
2. New files included in package

admin/includes/functions/extra_functions/functions_vatmod.php
admin/includes/languages/english/extra_definitions/vatmod.php

catalog/includes/functions/extra_functions/functions_vatmod.php
catalog/includes/languages/english/extra_definitions/vatmod.php
===========================
3. Modified files included in package
admin/customers.php
admin/invoice.php
admin/orders.php
admin/packingslip.php
admin/includes/classes/order.php
admin/includes/functions/functions_customers.php

catalog/includes/classes/order.php
catalog/includes/functions/functions_customers.php
catalog/includes/functions/functions_taxes.php
catalog/includes/modules/checkout_new_address.php
catalog/includes/modules/create_account.php
catalog/includes/modules/order_total/ot_shipping.php
catalog/includes/modules/pages/address_book_process/header_php.php
catalog/includes/modules/pages/address_book_process/jscript_main.php
catalog/includes/modules/pages/checkout_payment_address/jscript_main.php
catalog/includes/modules/pages/checkout_shipping_address/jscript_main.php
catalog/includes/modules/pages/create_account/jscript_form_check.php

catalog/includes/templates/YOUR_TEMPLATE/templates/tpl_modules_address_book_details.php
catalog/includes/templates/YOUR_TEMPLATE/templates/tpl_modules_checkout_new_address.php
catalog/includes/templates/YOUR_TEMPLATE/templates/tpl_modules_create_account.php
===========================
4. Modified files in admin/ & catalog/
For zencart's already modified versions, do a file compare and apply the code changes to your files (don't forget the 4 new files).
===========================
C. Configure the Shop
Log in as admin and make sure the following settings are true.

Configure->My Store->Country = Your Country (within EU)
Configure->My Store->Basis of Product Tax = Shipping
Configure->My Store->Basis of Shipping Tax = Shipping
Locations / Taxes-> Zone Definitions = Your Country (ie "Sweden") -> Insert Your Conutry (ie "Sweden")
Locations / Taxes-> Zone Definitions = "EU" -> Insert All Countries in EU, Except Your Country.
Locations / Taxes-> Tax Classes = Your Tax Class (ie "VAT")
Locations / Taxes-> Tax Rates = Your Tax Rate. Set Your Tax Class and Your Zone (ie "Moms", "Sweden", "25", "Moms (VAT) 25%", 1)
Locations / Taxes-> Tax Rates = Your Tax Rate. Set Your Tax Class and "EU" Zone (ie "Moms", "EU", "25", "VAT (Moms) 25%", 2)

If you want to you can have more zones for countries outside EU. Just create the Zone Definitions you need and assign tax to the zones in Tax Rates. In order for the prices to show with the correct tax, set priority as follows: EU 1, Sweden 2 and World 3. If you don't get it right, laborate with the priorities.
===========================
Good luck!
We hope you will like this Mod and find it usefull.
If you have any questions or suggestions - Feel free to say it at http://www.zen-cart.com/forum/showthread.php?p=201772

Sebastian Bergquist/Beez (http://www.sweetfabrik.se) & Viktor Bergquist/vike
