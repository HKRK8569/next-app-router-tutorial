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
