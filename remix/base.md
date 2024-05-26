# Remix

## Tutorial
- `routes/contacts.$contactId.tsx`はURI:`/contacts/${contact.id}`になる
- 編集画面URI:`/contacts/${contact.id}/edit`を加えたいときは
  - `routes/contacts.$contactid_.edit.tsx`にする
  - ~~末尾`_`で重複を許す？~~
  - `_.actionName.tsx`への遷移・処理移行は`<Form action="actionName"><button type="submit"> </button></Form>`から飛べる
- `export default`はページとなる
- 以下は便利解釈関数ら
  - `export const action`
    - `<Form method="post"><button type="submit">New</button></Form>`の処理をやってくれる
    - `routes/contacts.$contactid_.destroy.tsx`で`export const action`していたら
      - `routes/contacts.$contactid.tsx`内の`<Form action="destroy" method="post"></Form>`の処理受け口になってくれる
  - `export const loader`
    - `useLoaderData<typeof loader>()`とセット
    - データロードAPI
