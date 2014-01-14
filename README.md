salesforce1-uk-demo-data
========================


(1) Login to your developer edition salesforce environment
(2) Install the Warehouse App: http://bit.ly/s1package
(3) Open Developer Console in your salesforce environment & paste into the execute box the following code:

		Contact contact = new Contact(FirstName='Lloyd',LastName='Benjamin',MobilePhone='415-555-9473');
        insert contact;
        
        /* Create Accounts */
        Account a1 = new Account(Name='Heighway Associates',Type='Technology Partner',Industry='Telecommunications',BillingStreet='34 West Street',BillingCity='Marlow',BillingState='Berkshire',BillingPostalCode='SL72NB',ShippingStreet='34 West Street',ShippingCity='Marlow',ShippingState='Berkshire',ShippingPostalCode='SL72NB',Phone='01628 1234 235',Business_Hours__c='9am - 6pm, M-F',Location__Latitude__s=51.573435, Location__Longitude__s=-0.777111);
        insert a1;
        
        Account a2 = new Account(Name='Bauer Media',Type='Customer - Direct',Industry='Telecommunications',BillingStreet='189 SHAFTESBURY AVENUE',BillingCity='London',BillingState='London',BillingPostalCode='WC2H 8JG',ShippingStreet='189 SHAFTESBURY AVENUE',ShippingCity='London',ShippingState='London',ShippingPostalCode='WC2H 8JG',Phone='0203 3453 245',Business_Hours__c='8am - 7pm, M-F',Location__Latitude__s=51.515223, Location__Longitude__s=-0.127288, NumberOfEmployees=10,Parent=a1);
        insert a2;
        
        /*Create Account Contacts */
        List<AccountContactRole> aContacts = new List<AccountContactRole>();
        aContacts.add(new AccountContactRole(ContactId=contact.Id, AccountId=a1.Id));
        aContacts.add(new AccountContactRole(ContactId=contact.Id, AccountId=a2.Id));
        insert aContacts;
        
        /* Create Warehouses */
        List<Warehouse__c> warehouses = new List<Warehouse__c>();
		warehouses.add(new Warehouse__c(Name='Aloha Warehouse',City__c='Reading',Location__Longitude__s=-0.961304,Location__Latitude__s=51.430842,Street_Address__c='High Street',Phone__c='0207 234 234'));
		warehouses.add(new Warehouse__c(Name='Big Tech Warehouse',City__c='St. Albans',Location__Longitude__s=-0.352936,Location__Latitude__s=51.752739,Street_Address__c='High Street',Phone__c='208 234 234'));
		warehouses.add(new Warehouse__c(Name='Ferguson Home and Office',City__c='Milton Keynes',Location__Longitude__s=-0.748444,Location__Latitude__s=52.031571,Street_Address__c='High Street',Phone__c='209 234 234'));
		warehouses.add(new Warehouse__c(Name='Ferry Building Depot',City__c='Croydon',Location__Longitude__s=-0.09201,Location__Latitude__s=51.371981,Street_Address__c='High Street',Phone__c='210 234 234'));
		warehouses.add(new Warehouse__c(Name='Gateway Warehouse',City__c='Nottingham',Location__Longitude__s=-1.160431,Location__Latitude__s=52.943039,Street_Address__c='1807 Telegraph Ave',Phone__c='211 234 234'));
		warehouses.add(new Warehouse__c(Name='Kelly Paper Source',City__c='Walsall',Location__Longitude__s=-1.985779,Location__Latitude__s=52.584056,Street_Address__c='1808 Telegraph Ave',Phone__c='212 234 234'));
		warehouses.add(new Warehouse__c(Name='Marin Factory Store',City__c='Derby',Location__Longitude__s=-1.463928,Location__Latitude__s=52.90929,Street_Address__c='1809 Telegraph Ave',Phone__c='213 234 234'));
		warehouses.add(new Warehouse__c(Name='Our Warehouses Ltd',City__c='Swindon',Location__Longitude__s=-1.774292,Location__Latitude__s=51.551859,Street_Address__c='Ind. Path',Phone__c='214 234 234'));
		warehouses.add(new Warehouse__c(Name='Private Spaces',City__c='Sheffield',Location__Longitude__s=-1.472168,Location__Latitude__s=53.36241,Street_Address__c='High Street',Phone__c='215 234 234'));
		warehouses.add(new Warehouse__c(Name='Rent-a-Outlet',City__c='Slough',Location__Longitude__s=-0.600128,Location__Latitude__s=51.508943,Street_Address__c='190 High Road',Phone__c='216 234 234'));
		warehouses.add(new Warehouse__c(Name='S H Frank & Company',City__c='Stockport',Location__Longitude__s=-2.197266,Location__Latitude__s=53.39354,Street_Address__c='191 High Road',Phone__c='217 234 234'));
		warehouses.add(new Warehouse__c(Name='San Francisco Tech Mart',City__c='Liverpool',Location__Longitude__s=-2.993774,Location__Latitude__s=53.425274,Street_Address__c='Docks',Phone__c='218 234 234'));

        insert warehouses;

        /* Create Merchandise */
        List<Merchandise__c> m = new List<Merchandise__c>();
        m.add(new Merchandise__c(Name='Laptop',Price__c=500,Quantity__c=1000, Warehouse__c=warehouses[0].Id));
        m.add(new Merchandise__c(Name='Desktop',Price__c=1000,Quantity__c=500, Warehouse__c=warehouses[1].Id));
        m.add(new Merchandise__c(Name='Tablet',Price__c=300,Quantity__c=5000, Warehouse__c=warehouses[2].Id));
        m.add(new Merchandise__c(Name='Rack Server',Price__c=3245.99,Quantity__c=500, Warehouse__c=warehouses[3].Id));
        m.add(new Merchandise__c(Name='Windows Laptop',Price__c=445.99,Quantity__c=50, Warehouse__c=warehouses[4].Id));
        m.add(new Merchandise__c(Name='MacBook Air',Price__c=1345.00,Quantity__c=50, Warehouse__c=warehouses[5].Id));
        m.add(new Merchandise__c(Name='MacBook Pro',Price__c=1845.00,Quantity__c=50, Warehouse__c=warehouses[6].Id));
        m.add(new Merchandise__c(Name='Android',Price__c=1399.99,Quantity__c=250, Warehouse__c=warehouses[7].Id));
        m.add(new Merchandise__c(Name='iPhone 5S Gold',Price__c=600.00,Quantity__c=750, Warehouse__c=warehouses[8].Id));
        m.add(new Merchandise__c(Name='iPhone 5C Green',Price__c=600.00,Quantity__c=1200, Warehouse__c=warehouses[9].Id));
        m.add(new Merchandise__c(Name='iPhone 5S Gold',Price__c=600.00,Quantity__c=550, Warehouse__c=warehouses[10].Id));
        m.add(new Merchandise__c(Name='iPhone 5C Red',Price__c=600.00,Quantity__c=1850, Warehouse__c=warehouses[11].Id));  
        m.add(new Merchandise__c(Name='iPhone 5C Blue',Price__c=600.00,Quantity__c=2050, Warehouse__c=warehouses[11].Id));
        
        m.add(new Merchandise__c(Name='iPhone 5S Gold',Price__c=600.00,Quantity__c=750, Warehouse__c=warehouses[2].Id));
        m.add(new Merchandise__c(Name='iPhone 5C Green',Price__c=600.00,Quantity__c=1200, Warehouse__c=warehouses[5].Id));
        m.add(new Merchandise__c(Name='iPhone 5S Gold',Price__c=600.00,Quantity__c=550, Warehouse__c=warehouses[6].Id));
        m.add(new Merchandise__c(Name='iPhone 5C Red',Price__c=600.00,Quantity__c=1850, Warehouse__c=warehouses[8].Id));  
        m.add(new Merchandise__c(Name='iPhone 5C Blue',Price__c=600.00,Quantity__c=2050, Warehouse__c=warehouses[9].Id)); 
        
        m.add(new Merchandise__c(Name='iPhone 5S Gold',Price__c=600.00,Quantity__c=375, Warehouse__c=warehouses[5].Id));
        m.add(new Merchandise__c(Name='iPhone 5C Green',Price__c=600.00,Quantity__c=1400, Warehouse__c=warehouses[2].Id));
        m.add(new Merchandise__c(Name='iPhone 5S Gold',Price__c=600.00,Quantity__c=600, Warehouse__c=warehouses[8].Id));
        m.add(new Merchandise__c(Name='iPhone 5C Red',Price__c=600.00,Quantity__c=1475, Warehouse__c=warehouses[9].Id));  
        m.add(new Merchandise__c(Name='iPhone 5C Blue',Price__c=600.00,Quantity__c=1230, Warehouse__c=warehouses[2].Id));
        insert m;
        
        /* Create Invoices with line items */
        for (Integer i=0; i<=9; i++) {
            Invoice__c inv = new Invoice__c(Status__c=(i < 3 ? 'Closed' : 'Open'),Account__c=(i < 5 ? a1.Id : a2.Id));
            insert inv;
            
            Line_Item__c li = new Line_Item__c
              (Quantity__c=1, Merchandise__c=m[i].Id,Invoice__c=inv.Id);
            insert li;       
        }
        
        
        