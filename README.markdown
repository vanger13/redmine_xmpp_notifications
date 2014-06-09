# XMPP Notifications Plugin for Redmine

Данная версия будет работать только с Ruby 1.9+

This plugin is intended to provide basic integration with XMPP messenger (Jabber).
Following actions will result in notifications to Jabber:

- Create and update issues

## Installation & Configuration

И так установим данный девайс в Ваш Redmime

для начала идем туда геде у вас установленн сам RedMine, а там уже
```
cd plugins/

```
Ну конечно мы тут не обойдемся без самого плагина
```
git clone https://github.com/vanger13/redmine_xmpp_notifications.git
```
Осталось только установить.
Установим звисимости gem
```
bundle install
```
Остался последний штрих.
```
cd ..
rake redmine:plugins:migrate RAILS_ENV=production

```
ах ну да, не забудьте перезапустить RedMine
в зависимости от того как он у вас запущен в моем случае это:
```
service redmine restart
service nginx restart
```
в случае Apache и passanger будет достаточно
```
service apache2 restart
```

- The XMPP Notifications Plugin depends on the [Xmpp4r-Simple](http://xmpp4r-simple.rubyforge.org/). This can be installed with:
    $ sudo gem install xmpp4r-simple
- Then install the Plugin following the general Redmine [plugin installation instructions](http://www.redmine.org/wiki/redmine/Plugins).
- Go to the Plugins section of the Administration page, select Configure.
- On this page fill out the Jabber ID and password for user who will sends messages.
- Restart your Redmine web servers (e.g. mongrel, thin, mod_rails).