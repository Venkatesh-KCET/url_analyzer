# Extracts useful data from urls (domain, subdomains, top level ...)

```php
# Tested with:
# PHP 8
# ubuntu 22.04

composer require venkatesh-kcet/url_analyzer


require_once __DIR__ . '/vendor/autoload.php';
use VenkateshKcet\UrlAnalyzer\index;
$url_analyzer = new index();

$df = $url_analyzer->get_all_links_from_html("https://github.com/hansalemaos/getevent_sendevent", '<html>...</html>');


$df = $url_analyzer->get_all_links_from_url("https://github.com/hansalemaos/getevent_sendevent");
print_r($df);

$allurls = [
    "https://gist.github.com/",
    "https://pypi.org/project/window2video/",
    "https://github.dev/",
    "https://docs.github.com/articles/which-remote-url-should-i-use",
    "https://cli.github.com/",
    "x-github-client://openRepo/https://github.com/hansalemaos/window2video",
    "https://desktop.github.com/",
    "https://developer.apple.com/xcode/",
    "/window2video/main/LICENSE",
    "/window2video/main/README.MD",
    "/window2video/main/__init__.py",
    "/window2video/main/requirements.txt",
    "/window2video/main/thirdparty.json",
    "https://docs.github.com/en/github/site-policy/github-terms-of-service",
    "https://docs.github.com/en/github/site-policy/github-privacy-statement",
    "https://www.githubstatus.com/",
    "https://docs.github.com/",
    "https://support.github.com/?tags=dotcom-footer",
    "https://services.github.com/",
    "https://github.blog/",
];
$df2 = $url_analyzer->get_url_df($allurls, "https://raw.githubusercontent.com/hansalemaos/");

print_r($df2);


```
