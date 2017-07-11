
## 使い方
`~/.vim/bundle/neosnippet-snippets/snippets`<br>
上記ディレクトリに`go.snip`を配置<br>

`.vimrc`に下記を追加<br>
`let g:neosnippet#snippets_directory='~/.vim/bundle/neosnippet-snippets/snippets/'`
<br>
さらにsnippet用のコマンドの設定
```
" <TAB>: completion.
" inoremap <expr><TAB>  pumvisible() ? "\<C-n>" : "\<TAB>"
inoremap <expr><S-TAB>  pumvisible() ? "\<C-p>" : "\<S-TAB>"

" Plugin key-mappings.
imap <C-k>     <Plug>(neosnippet_expand_or_jump)
smap <C-k>     <Plug>(neosnippet_expand_or_jump)

" SuperTab like snippets behavior.
" imap <expr><TAB> neosnippet#jumpable() ? "\<Plug>(neosnippet_expand_or_jump)" : pumvisible() ? "\<C-n>" : "\<TAB>"
imap <expr><TAB> pumvisible() ? "\<C-n>" : neosnippet#jumpable() ? "\<Plug>(neosnippet_expand_or_jump)" : "\<TAB>"
smap <expr><TAB> neosnippet#jumpable() ? "\<Plug>(neosnippet_expand_or_jump)" : "\<TAB>"

" For snippet_complete marker.
if has('conceal')
  set conceallevel=2 concealcursor=i
endif
```
を追加

.goファイルで`goa`と打ち込んでTABで選択して`Ctrl+k`で展開
