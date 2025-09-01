# Vim Learning Journey - Day 01

## Resources

* [Vim Tutorial Series (YouTube Playlist by ThePrimeagen)](https://www.youtube.com/watch?v=X6AR2RMB5tE&list=PLm323Lc7iSW_wuxqmKx_xxNtJC_hJbQ7R)
* [Learn Vim Quickly (YouTube by freeCodeCamp)](https://youtu.be/RZ4p-saaQkc)

## What I Did Today

* Set up my learning plan using video tutorials.
* Began exploring the basics of Vim to understand its modal editing system.

## Key Takeaways

* Vim uses **modes** (Normal, Insert, Visual, Command).
* Navigation and editing in Vim are designed to minimize use of the mouse.
* The learning curve may be steep, but practice will make it faster over time.

## Reflection

Today I mainly gathered learning resources and got an overview of what to expect. The challenge is getting comfortable with a completely new way of editing text, but I’m excited to continue.
**Next step:** Start practicing basic movements and commands (`h`, `j`, `k`, `l`, `i`, `:wq`, etc.) in Vim.



# Vim learning Journey - Day 02

## What I Did Today

* Created and edited my Vim configuration file (`~/.vimrc`).
* Practiced basic motions:

  * `h`, `j`, `k`, `l` (left, down, up, right)
  * `i` (insert mode)
* Learned new scrolling motions:

  * `<C-u>` – scroll up half a page
  * `<C-d>` – scroll down half a page
  * `<C-b>` – scroll up a full page
  * `<C-f>` – scroll down a full page
  * `zz` – recenters the current line

* Customized Vim shortcuts and settings using `inoremap` and `nnoremap`.

### Customizations

* Enabled line numbering
* Enabled relative numbering
* Turned on auto-indent
* Set tabstop
* Created a custom shortcut to save files with `CTRL + s`

  ```vim
  nnoremap <C-s> :w<CR>
  ```

## Reflection

Today I focused on **practical Vim configuration** and **basic navigation**. The challenge was remembering the new motions and key mappings, but creating custom shortcuts made editing much faster.
**Next step:** Continue exploring more motions and experiment with additional Vim settings to improve workflow.




















