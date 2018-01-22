# WP RSS Bridge

Use social network data in you WP project.

Based on [RSS Bridge](https://github.com/RSS-Bridge/rss-bridge/)

Data are cached for better performances.

## Usage

```
$bridges = array(
    "Facebook" => array(
        'u' => 'zuck',
        'media_type' => 'all'
    ),
    "Twitter" => array(
        'u' => 'Jack',
        'norep' => 'on'
    ),
    "Instagram" => array(
        'u' => 'kimkardashian'
    )
);
$processor = new Wp_Rss_Bridge_Processor($bridges);
$data = $processor->get_data();
```

Default cache timeout is 24h. This can be changed using : 

```
$processor = new Wp_Rss_Bridge_Processor($bridges, 60); // Second parameter is cache timeout in seconds.
```

Finally, it's also possible to change the user agent ued when querying data : 

```
$processor = new Wp_Rss_Bridge_Processor($bridges, 60, "User Agent");
```

### Bridges

Each bridge has its own settings, defined in its own PHP class in RSS Bridge. See RSS Bridge Documentation and source code for more.