Initiaisation
=============

- Install dependencies with : 
    php composer.phar install

- Configure '.htaccess' (change RewriteBase line)
    vi .htaccess
    
- Configure 'build.properties'
    change 'propel.project'.
    change 'propel.database.url'.
    change 'propel.database.user'.
    change 'propel.database.password'.
    
- Configure 'runtime-conf.xml'
    change datasources 'default'.
    change datasourc 'id'.
    change dns/user/password
    
- Execute 
    vendor/propel/propel1/generator/bin/propel-gen
    and 
    vendor/propel/propel1/generator/bin/propel-gen insert-sql
    
- Uncomment to active propel
    $app->register(new Propel\Silex\PropelServiceProvider(), array(
    'propel.config_file' => __DIR__ . '/../config/site-conf.php',
    'propel.model_path'  => __DIR__ . '/../src',
    ));
