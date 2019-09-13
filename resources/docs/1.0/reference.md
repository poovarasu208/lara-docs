# Reference
- [Heading](#heading)
    - [Level 2 Heading](#heading2)
    - [Level 3 Heading](#heading3)
    - [Level 4 Heading](#heading4)
- [Text](#text)
    - [Bold Text](#bold-text)
    - [Italic Text](#italic-text)
- [List and Table](#list-and-table)
    - [Content List](#list)
    - [Table](#table)
- [Inline Link](#inline-link)
- [Quote](#quote)
    - [Inline Quote](#inline-quote)
    - [Block Quote](#block-quote)
- [Hint](#hint)
    - [Tip Hint](#tip-hint)
    - [Note Hint](#note-hint)
    - [Video Hint](#video-hint)
- [Image](#image)

<a name="heading"></a>
# Level 1 Heading
<a name="heading2"></a>
## Level 2 Heading
<a name="heading3"></a>
### Level 3 Heading
<a name="heading4"></a>
#### Level 4 Heading

<a name="text"></a>
## Text

<a name="bold-text"></a>
### Bold Text
This text is **bold** in style.

<a name="italic-text"></a>
### Italic Text
This text is *italic* in style.

<a name="list-and-table"></a>
#### List and Table

<a name="list"></a>
### Content List
<div class="content-list" markdown="1">
- Item 1
- Item 2
- [Item holding link](#)
</div>
    
<a name="table"></a>
### Table
| Version | Release | Bug Fixes Until | Security Fixes Until |
| --- | --- | --- | --- |
| 5.0 | February 4th, 2015 | August 4th, 2015 | February 4th, 2016 |
| 5.1 (LTS) | June 9th, 2015 | June 9th, 2017 | June 9th, 2018 |
| 5.2 | December 21st, 2015 | June 21st, 2016 | December 21st, 2016 |
| 5.3 | August 23rd, 2016 | February 23rd, 2017 | August 23rd, 2017 |
| 5.4 | January 24th, 2017 | July 24th, 2017 | January 24th, 2018 |
| 5.5 (LTS) | August 30th, 2017 | August 30th, 2019 | August 30th, 2020 |
| 5.6 | February 7th, 2018 | August 7th, 2018 | February 7th, 2019 |

<a name="inline-link"></a>
## Inline Quote
This is a link to [Php Manual](/)

<a name="quote"></a>
## Quote

<a name="inline-quote"></a>
### Inline Quote
Some `content` goes here. It will apply the `color` related to the `quote` content automatically.

<a name="block-quote"></a>
### Block Quote
```php
Some content goes here..
```
    
#### Another Example
```php
$schedule->command('report:generate')
         ->fridays()
         ->at('17:00')
         ->onOneServer();
```

<a name="hint"></a>
## Hint

<a name="tip-hint"></a>
### Tip Hint
> {primary} This documentation summarizes the most notable improvements to the framework; however, more thorough change logs are always available [`on GitHub`](https://github.com/laravel/framework/blob/5.6/CHANGELOG-5.6.md).

<a name="note-hint"></a>
### Note Hint
> {info} To utilize this feature, your application must be using the `memcached` or `redis` cache driver as your application's default cache driver. In addition, all servers must be communicating with the same central cache server.

<a name="video-hint"></a>
### Video Hint
> {success} Laracasts provides a free, thorough [`introduction to Laravel`](http://laravelfromscratch.com) for newcomers to the framework. It's a great place to start your journey.

<a name="image"></a>
## Image
This is a `image`
<img src="https://raw.githubusercontent.com/nunomaduro/collision/stable/docs/example.png" width="600" height="388">

