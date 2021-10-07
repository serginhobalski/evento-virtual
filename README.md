[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/git/external?repository-url=https%3A%2F%2Fgithub.com%2Fvercel%2Fvirtual-event-starter-kit&project-name=virtual-event-starter-kit&repository-name=virtual-event-starter-kit&demo-title=Virtual%20Event%20Starter%20Kit&demo-description=Jumpstart%20your%20virtual%20event%20and%20scale%20to%20any%20size%20with%20Next.js%20and%20Vercel.&demo-url=https%3A%2F%2Fdemo.vercel.events%2F&demo-image=https%3A%2F%2Fdemo.vercel.events%2Fdeploy.png&integration-ids=oac_I1h8Dm9Mf30VNb3xQ0hebYvS&external-id=%7B%22manifest%22%3A%20%22https%3A%2F%2Fraw.githubusercontent.com%2Fvercel%2Fvirtual-event-starter-kit%2Fmain%2Fdatocms.json%22%7D)

# [Kit Inicial para Evento Virtual](https://vercel.com/virtual-event-starter-kit)

### Demo: https://demo.vercel.events

Esse kit de para Evento Virtual foi desenvolvido tendo como modelo a [Next.js Conf 2020](https://nextjs.org/2020/conf), que realizou mais de  40.000 atendimentos ao vivo. Este pacote inclui os seguintes recursos:

- Múltiplos estágios com a incorparação de um YouTube stream.
- Exposição de patrocinadores, incluindo tanto os individuais como os virtuais.
- Career Fair, allowing attendees to network and find job opportunties
- Criação e registro de ingresso
- Páginas de interação e bios
- Agenda

Essa plataforma foi construída com base nos princípios:

- **Delegação:** Realizar uma conferência é difícil – você deve **delegar** tarefas a terceiros para obter sucesso. Alguns elementos de uma conferência online são difíceis de acertar, por isso é preferível confiar em quem já possui experiência no assunto.
- **Flexibilidade:** Embora delegar certos elementos da conferência seja útil, também é importante possuir uma plataforma. É por isso que este modelo fornece uma base de código aberto **flexível** que pode ser modificada para o seu evento.
- **Redução de riscos:** É inevitável que algo dê errado durante o seu evento. Essa plataforma **reduz riscos** apoiando-se em um site dinâmico que produz arquivos estáticos usando [Incremental Static Generation](https://nextjs.org/docs/basic-features/data-fetching). Esses arquivos estáticos são armazenados em cache, garantindo que seu site nunca fique inativo. Então, ele usa [API Routes](https://nextjs.org/docs/api-routes/introduction) para espalhar conteúdo dinâmico no topo, que é hospedado por um provedor com 99,99% de tempo de atividade.

### Construção

- Framework: [Next.js](https://nextjs.org)
  - [CSS Modules](https://nextjs.org/docs/basic-features/built-in-css-support)
  - [TypeScript](https://nextjs.org/docs/basic-features/typescript)
- CMS: [Multiple Options](#cms)
- Vídeos: [YouTube](https://www.youtube.com)
- Deployment: [Vercel](https://vercel.com)
- Autenticação: [GitHub OAuth](https://docs.github.com/en/free-pro-team@latest/developers/apps/authorizing-oauth-apps)
- Database: [Redis](https://redis.io)

## Executando Localmente

Primeiro, defina as variáveis de ambiente locais. Foi incluído um token de acesso DatoCMS somente leitura que você pode usar em `.env.local.example`.

```
cp .env.local.example .env.local
```

Em seguida, instale os pacotes e execute o servidor de desenvolvimento:

```bash
yarn install
yarn dev
```

Abra [http://localhost:3000](http://localhost:3000) com seu navegador para ver o resultado.

## Clone and Deploy

Click no botão abaixo para clonar e fazer o deploy deste template no [Vercel](https://vercel.com/).

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/git/external?repository-url=https%3A%2F%2Fgithub.com%2Fvercel%2Fvirtual-event-starter-kit&project-name=virtual-event-starter-kit&repository-name=virtual-event-starter-kit&demo-title=Virtual%20Event%20Starter%20Kit&demo-description=Jumpstart%20your%20virtual%20event%20and%20scale%20to%20any%20size%20with%20Next.js%20and%20Vercel.&demo-url=https%3A%2F%2Fdemo.vercel.events%2F&demo-image=https%3A%2F%2Fdemo.vercel.events%2Fdeploy.png&integration-ids=oac_I1h8Dm9Mf30VNb3xQ0hebYvS&external-id=%7B%22manifest%22%3A%20%22https%3A%2F%2Fraw.githubusercontent.com%2Fvercel%2Fvirtual-event-starter-kit%2Fmain%2Fdatocms.json%22%7D)

Você será solicitado a instalar a integração do [DatoCMS](https://www.datocms.com). Ele permite que você se inscreva ou faça login no DatoCMS e crie um novo projeto DatoCMS com base nos dados (palestrantes, sessões, etc.) usados na demonstração.

## Customize

### CMS

Variáveis de ambiente determinam qual CMS usar. Veja [`lib/cms-api.ts`](lib/cms-api.ts) para maiores detalhes e `.env.local.example` para todas as variáveis de ambiente. A demo ([demo.vercel.events](https://demo.vercel.events)) usa DatoCMS, mas também é suportada por:

- [Agility](https://vercel.com/new/git/external?repository-url=https%3A%2F%2Fgithub.com%2Fvercel%2Fvirtual-event-starter-kit&project-name=virtual-event-starter-kit&repository-name=virtual-event-starter-kit&demo-title=Virtual%20Event%20Starter%20Kit&demo-description=Jumpstart%20your%20virtual%20event%20and%20scale%20to%20any%20size%20with%20Next.js%20and%20Vercel.&demo-url=https%3A%2F%2Fdemo.vercel.events%2F&demo-image=https%3A%2F%2Fdemo.vercel.events%2Fdeploy.png&integration-ids=oac_Dnqk9CoC6rZ18k9nVR9KresV&external-id=%7B%22manifest%22%3A%20%22https%3A%2F%2Fraw.githubusercontent.com%2Fvercel%2Fvirtual-event-starter-kit%2Fmain%2Fdatocms.json%22%2C%20%22githubRepo%22%3A%20%22vercel%2Fvirtual-event-starter-kit%22%7D)
- [Contentful](lib/cms-providers/contentful.ts)
- [Prismic](lib/cms-providers/prismic/index.ts) ([Instructions](lib/cms-providers/prismic/README.md))
- [Sanity](https://create.sanity.io/?template=sanity-io%2Fsanity-template-nextjs-event-starter)
- [Storyblok](lib/cms-providers/storyblok.ts) 
  - Click the following link to create the space for this starter kit in Storyblok: [Create Event Space](https://app.storyblok.com/#!/build/101757)

### Constants

`lib/constants.ts` contains a list of variables you should customize.

## Authentication and Database

Some features won’t work until you set up authentication and database. The demo ([demo.vercel.events](https://demo.vercel.events)) uses [GitHub OAuth](https://docs.github.com/en/free-pro-team@latest/developers/apps/creating-an-oauth-app) for authentication and [Redis](https://redis.io/) for database. You can use different providers as you see fit.

### Authentication

You need to have GitHub OAuth set up to be able to customize the ticket after signing up on the registration form.

First, create a [GitHub OAuth application](https://docs.github.com/en/free-pro-team@latest/developers/apps/creating-an-oauth-app) to use for authentication.

- Set **Authorization Callback URL** as `<your domain>/api/github-oauth`
- After creating the OAuth app, create a **client secret**.

#### Running Locally:

- Set the Authorization Callback URL as `http://localhost:3000/api/github-oauth` on GitHub.
- On `.env.local`, set `NEXT_PUBLIC_GITHUB_OAUTH_CLIENT_ID` as the **Client ID** of the OAuth app.
- Set `GITHUB_OAUTH_CLIENT_SECRET` as the **Client secret** of the OAuth app.
- Finally, make sure the `NEXT_PUBLIC_SITE_ORIGIN` environment variable is set as `http://localhost:3000`. This is required to get the OAuth popup to work locally.
- Restart the app (`yarn dev`) after editing `.env.local`.

Once it’s set up, sign up using the registration form on the home page (not on a stage page) and then click "Generate with GitHub".

#### On Vercel:

- Set the Authorization Callback URL as `<your deployment’s URL>/api/github-oauth` on GitHub.
- Set `NEXT_PUBLIC_GITHUB_OAUTH_CLIENT_ID` and `GITHUB_OAUTH_CLIENT_SECRET` on [Vercel Project Environment Variables Settings](https://vercel.com/docs/environment-variables) for the production environment.
- Edit `SITE_URL` in `lib/constants.ts` to match your deployment’s URL (no trailing slash).
- Push the code to redeploy the Project on Vercel.

### Database

You need a database to save user data and enable the following features:

- Generating a unique ticket number for each email when signing up on the registration form. If DB is not set up, it’ll always be `1234`.
- Generating a unique ticket image or ticket URL after signing in with GitHub. If DB is not set up, each ticket image or URL will show generic data.

The demo ([demo.vercel.events](https://demo.vercel.events)) uses [Redis](https://redis.io/), but you can customize it to use any database you like.

#### Running Redis Locally

1. Install Redis locally and run it.
2. Specify the following in `.env.local`:

```
REDIS_PORT=6379 # Default Redis port number
REDIS_URL=localhost
REDIS_PASSWORD=
REDIS_SSL_ENABLED=
REDIS_EMAIL_TO_ID_SECRET=foo # Come up with your own secret string
```

> `REDIS_EMAIL_TO_ID_SECRET` will be used to create a hash of the email address, which will be used for the Redis key for each user data (i.e. `id:<hash>`). See `lib/redis.ts` for details.

> If your Redis server has SSL (TLS) encryption enabled then set REDIS_SSL_ENABLED=true

3. Restart the app (`yarn dev`) after editing `.env.local`.
4. In a separate terminal window, start the Next.js dev server (`yarn dev`) and sign up using the registration form.
5. In a separate terminal window, run Redis CLI, list keys (`keys *`) and inspect a `id:<hash>` key (`hgetall id:<hash>`). You should see the newly registered user.

#### Using Redis On Vercel

Provision your own Redis instance and set `REDIS_PORT`, `REDIS_URL`, `REDIS_PASSWORD`, `REDIS_SSL_ENABLED` and `REDIS_EMAIL_TO_ID_SECRET` (come up with your own secret string) on [Vercel Project Environment Variables Settings](https://vercel.com/docs/environment-variables) for the production environment.

If you do not want to maintain a Redis server, you can use [Upstash](https://upstash.com) which provides Serverless Redis with a free tier.

## More Details

### Stages

There are four different stages included in the seed data. Feel free to add or remove these based on your schedule. Each stage requires the user to enter their email to register with the conference before entering the event. After successfully entering their email and saving the user with your database of choice, the user is able to view the embedded YouTube stream. The login state is persisted as a `httponly` cookie.

One major feature of the conference platform is a near real-time sync with the CMS. Every five seconds, the stage queries `/api/stages` to fetch the latest information from the CMS. This allows you to make changes on the fly, without the user having the refresh the page. No need for websockets.

The primary use case for this is updating the YouTube embedded URL. Next.js Conf used this to seamlessly switch between pre-recorded videos running as a live premiere, and truly live content (e.g. panels). Plus, we had a few instances where our schedule needed to be tweaked on the fly. This implementation is fault tolerant, as well. The API route is properly cached and if the CMS was to somewhow go down, it won't break the page.

### Schedule / Speaker Pages

Schedule and speaker information is hosted in the CMS. The demo ([demo.vercel.events](https://demo.vercel.events)) is seeded with images from Unsplash and a placeholder schedule. Each speaker has their own page with an image, bio, social media links, and information about their talk. The schedule is also shown as a sidebar on each corresponding stage.

### Sponsor Expo

If you'd like to have your event sponsored, the Expo provides a platform to showcase sponsors with:

- Their logo
- Four call-to-action links
- Embedded YouTube video
- Link to chat room (Discord)

For Next.js Conf, we created a Discord channel for each sponsor.

### Career Fair

Networking is vital for in-person conferences and replicating that environment virtually poses a challege. For the Career Fair, this starter provides the ability to list job postings, as well as an external link to talk with the company's recruiters on Discord.

### Adding Discord Chat

For Next.js Conf, we used Discord for conference attendees to chat. On each stage, we showed a highlighted message from the corresponding Discord channel. If a user in our allow list used the camera emoji (📸) it would show the message on the stage.

If you'd like to add similar functionality to your conference, you can use the [API route](https://nextjs.org/docs/api-routes/introduction) below to fetch messages after creating a Discord bot. This API route is set up with the proper caching headers and ensures you won't get rate-limited with high traffic.

```ts
import ms from 'ms';
import fetch, { Headers, RequestInit } from 'node-fetch';
import { NextApiRequest, NextApiResponse } from 'next';

interface Reaction {
  emoji: { name: string };
}

interface Message {
  id: string;
  channel_id: string;
  content: string;
  timestamp: string;
  author: {
    username: string;
  };
  reactions?: Reaction[];
}

interface ReactionSelector {
  id: string;
}

// After creating a bot, add the token as an environment var
const { DISCORD_BOT_TOKEN } = process.env;

// Number of seconds to cache the API response for
const EXPIRES_SECONDS = 60;

// Emoji that should be selected by a whitelisted user
// in order for this API to return the message
const EMOJI = '🎥';

// Whitelisted user IDs that are allowed to add the emoji to influence this API
const USERS = [
  '752552204124291104' // username
];

// Discord base API URL
const API = 'https://discordapp.com/api/';

// Map of Stage names to Discord channel IDs
const CHANNELS = new Map<string, string>([
  ['a', '769350098697191515'],
  ['c', '769350352226877549'],
  ['m', '769350396623192074'],
  ['e', '769350429644685351']
]);

const api = (url: string, opts: RequestInit = {}) => {
  const headers = new Headers(opts.headers);
  headers.set('Authorization', `Bot ${DISCORD_BOT_TOKEN}`);
  headers.set('User-Agent', 'Discord Bot (https://yoursite.com/conf, v0.1)');

  return fetch(`${API}${url}`, {
    ...opts,
    headers
  });
};

async function getReactionSelectors(
  channelId: string,
  messageId: string,
  emoji: string
): Promise<ReactionSelector[]> {
  const res = await api(
    `channels/${channelId}/messages/${messageId}/reactions/${encodeURIComponent(emoji)}`
  );
  if (!res.ok) {
    throw new Error(`Failed to get message reactions: ${await res.text()} (${res.status})`);
  }
  return res.json();
}

async function getLatestMessageWithEmoji(
  messages: Message[],
  emoji: string,
  usersWhitelist: string[]
) {
  for (const message of messages) {
    if (!message.content.trim()) {
      // Empty message, ignore
      // You could also filter messages here
      continue;
    }
    for (const reaction of message.reactions || []) {
      if (reaction.emoji.name === emoji) {
        const selectors = await getReactionSelectors(message.channel_id, message.id, emoji);
        const selector = selectors.find(r => usersWhitelist.includes(r.id));
        if (selector) {
          // The correct emoji was added from a whitelisted user
          return { message, selector };
        }
      }
    }
  }
}

export default async function getDiscordMessage(req: NextApiRequest, res: NextApiResponse) {
  const { stage } = req.query;
  if (typeof stage !== 'string') {
    return res.status(400).json({ error: 'Query parameter "stage" must be a string' });
  }

  const channelId = CHANNELS.get(stage);
  if (!channelId) {
    return res.status(400).json({ error: `Invalid "stage": ${stage}` });
  }

  const apiRes = await api(`channels/${channelId}/messages`);
  let messages: Message[] = [];
  if (apiRes.status !== 429 && apiRes.ok) {
    messages = await apiRes.json();
  }

  if (apiRes.status === 429) {
    const reset = apiRes.headers.get('X-RateLimit-Reset-After') || 5;
    res.setHeader(
      'Cache-Control',
      `s-maxage=${reset}, public, must-revalidate, stale-while-revalidate`
    );
  }

  const messageToShow = await getLatestMessageWithEmoji(messages, EMOJI, USERS);
  if (!messageToShow) {
    return res.status(404).json({ error: 'Could not find message with emoji' });
  }

  const body = {
    username: messageToShow.message.author.username,
    content: messageToShow.message.content,
    timestamp: messageToShow.message.timestamp
  };

  // Set caching headers
  const expires = new Date(Date.now() + ms(`${EXPIRES_SECONDS}s`));
  res.setHeader('Expires', expires.toUTCString());
  res.setHeader(
    'Cache-Control',
    `s-maxage=${EXPIRES_SECONDS}, immutable, must-revalidate, stale-while-revalidate`
  );

  return res.status(200).json(body);
}
```

### Demo

The demo is available at https://demo.vercel.events. The data recorded or used on the demo may be removed by Vercel at any point.
