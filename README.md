# think-session-redis2
Use `think-redis2` to store session for ThinkJS   
forked from https://github.com/thinkjs/think-session-redis

## Install

```
npm install think-redis2
npm install think-session-redis2
```

## How to use

config file `src/config/adapter.js`, add options:

```typescript
const redisSession = require('think-session-redis2');
exports.session = {
  type: 'redis',
  common: {
    cookie: {
      name: 'NODESESSID',
      maxAge: 24 * 3600 * 1000,
      domain: '',
      path: '/',
      httpOnly: true,
      sameSite: false,
      signed: false,
      overwrite: false
    }
  },
  redis: {
    redisName:"rc1", // => ctx.redis(options.redisName)
    handle: redisSession,
    maxAge: 3600 * 1000, // session timeout, if not set, session will be persistent.
    autoUpdate: false, // update expired time when get session, default is false
  }
}
```
