# PUPPET-MOCK

[![NPM Version](https://badge.fury.io/js/wechaty-puppet-mock.svg)](https://badge.fury.io/js/wechaty-puppet-mock)
[![npm (tag)](https://img.shields.io/npm/v/wechaty-puppet-mock/next.svg)](https://www.npmjs.com/package/wechaty-puppet-mock?activeTab=versions)
[![NPM](https://github.com/wechaty/wechaty-puppet-mock/workflows/NPM/badge.svg)](https://github.com/wechaty/wechaty-puppet-mock/actions?query=workflow%3ANPM)

![chatie puppet](https://wechaty.github.io/wechaty-puppet-mock/images/mock.png)

> Picture Credit: <https://softwareautotools.com/2017/03/01/mocking-explained-in-python/>

[![Powered by Wechaty](https://img.shields.io/badge/Powered%20By-Wechaty-brightgreen.svg)](https://github.com/wechaty/wechaty)
[![TypeScript](https://img.shields.io/badge/%3C%2F%3E-TypeScript-blue.svg)](https://www.typescriptlang.org/)

Puppet Mocker & Starter Template for Wechaty, it is very useful when you:

1. Want to test the Wechaty framework with a mock puppet, or
1. You want to write your own Puppet implenmentation.

Then `PuppetMock` will helps you a lot.

## USAGE

```ts
import { MemoryCard } from 'wechaty-puppet'
import { PuppetMock } from 'wechaty-puppet-mock'

const puppet  = new PuppetMock({ memory: new MemoryCard() })
const wechaty = new Wechaty({ puppet })
```

## API Reference

### Mocker

```ts
import { Wechaty }  from 'wechaty'
import { Mocker, PuppetMock }   from 'wechaty-puppet-mock'

const mocker = new Mocker()
const puppet = new PuppetMock({ mocker })
const bot = new Wechaty({ puppet })

await bot.start()

mocker.scan('https://github.com/wechaty', 1)

const user = mocker.createContact()
mocker.login(user)

const contact = mocker.createContact()
const room = mocker.createRoom()

user.say('Hello').to(contact)
contact.say('World').to(user)
```

## HELPER UTILITIES

### StateSwitch

```ts
this.state.on('pending')
this.state.on(true)
this.state.off('pending')
this.state.off(true)

await this.state.ready('on')
await this.state.ready('off')

```

### Watchdog

```ts
```

### MemoryCard

```ts
await memory.set('config', { id: 1, key: 'xxx' })
const config = await memory.get('config')
console.log(config)
// Output: { id: 1, key: 'xxx' }
```

## HISTORY

### master

### v0.22 (Jun 4, 2020)

`Mocker` Realeased. `Mocker` is a manager for controlling the behavior of the Puppet activities.

### v0.0.1 (Jun 27, 2018)

Initial version.

`PuppetMock` is a skelton Puppet without do anything, it will make testing easy when developing Wechaty

## AUTHOR

[Huan LI](http://linkedin.com/in/zixia) \<zixia@zixia.net\>

<a href="https://stackexchange.com/users/265499">
  <img src="https://stackexchange.com/users/flair/265499.png" width="208" height="58" alt="profile for zixia on Stack Exchange, a network of free, community-driven Q&amp;A sites" title="profile for zixia on Stack Exchange, a network of free, community-driven Q&amp;A sites">
</a>

## COPYRIGHT & LICENSE

* Code & Docs © 2018 Huan LI \<zixia@zixia.net\>
* Code released under the Apache-2.0 License
* Docs released under Creative Commons
