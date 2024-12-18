# nextMemo

## font

[next/font](https://nextjs.org/docs/pages/building-your-application/optimizing/fonts)を使う

build 時にフォントファイルをダウンロードしているためユーザーが追加でリクエストを送る必要がなく、パフォーマンスがいい

```
import { Inter, Lusitana } from "next/font/google";

export const inter = Inter({
  subsets: ["latin"],
});

export const lusitana = Lusitana({
  weight: ["400", "700"],
  subsets: ["latin"],
});

```

## image

[next/image](https://nextjs.org/docs/pages/api-reference/components/image)を利用する

自動で画像を最適化してくれる

```
import Image from 'next/image';

<Image
    src="/hero-desktop.png"
    width={1000}
    height={760}
    className="hidden md:block"
    alt="Screenshots of the dashboard project showing desktop version"
    />
```

## routing

app ディレクトリに任意の名前のディレクトリを作成してその中に page.tsx を作成すると自動的にルーティングされる

- TOP
  - /
- dashboard
  - /dashboard
- customers
  - /dashboard/customers

```
- app
   - page.tsx
   - dashboard
      - page.tsx
      - customers
         - page.tsx

```

()で囲んだディレクトリを作成した場合は URL には反映されない
下記二つは同義になる

```
- app
   - page.tsx
```

```
- app
   - (overview)
      - page.tsx
```

## layout

layout.tsx を配置している配下の page.tsx の共通部分を記述できる

## Link

[next/link](https://nextjs-ja-translation-docs.vercel.app/docs/api-reference/next/link)を利用する

Link コンポーネントが表示されると nextjs はルートのコードをプリフェッチする

```
import Link from 'next/link';

 <Link
    href="/"
  >Top</Link>
```

## usePathname

path を取得する関数
使用する場合は use client を記述する必要あり

https://nextjs.org/docs/app/api-reference/functions/use-pathname

## PPR

ページを静的なレンダリングをしつつ、必要な部分だけ動的なレンダリングを使うことができる

```
export const experimental_ppr = true;
```

next.config

```
const nextConfig = {
  experimental: {
    ppr: 'incremental',
  },
};

export default nextConfig;
```
