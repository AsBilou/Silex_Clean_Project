Silex archetype V1.2 (08/March/2013)

Initialisation
=============

- Install dependencies with : 
    php composer.phar install

- Configure '.htaccess' (change RewriteBase line)
    vi .htaccess

Propel
======

- Create your own database with phpmyadmin or other
    
- Configure 'build.properties'
    change 'propel.project'.
    change 'propel.database.url'.
    change 'propel.database.user'.
    change 'propel.database.password'.
    
- Configure 'runtime-conf.xml'
    change datasources 'default'.
    change datasource 'id'.
    change dns/user/password
    
- Execute 
    vendor/propel/propel1/generator/bin/propel-gen (generate class files)
    and 
    vendor/propel/propel1/generator/bin/propel-gen insert-sql (insert into database)
    
- Uncomment to active propel and rename site-conf.php with your conf file name
    $app->register(new Propel\Silex\PropelServiceProvider(), array(
    'propel.config_file' => __DIR__ . '/../config/site-conf.php',
    'propel.model_path'  => __DIR__ . '/../src',
    ));

Security
=============

- Configure security.firewalls register in bootstrap.php
