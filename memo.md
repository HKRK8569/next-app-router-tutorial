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
