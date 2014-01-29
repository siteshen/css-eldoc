# CSS Eldoc Plugin

This is css-eldoc, an eldoc-mode plugin for CSS source code.

Eldoc-mode is a MinorMode which shows you, in the echo area, the argument list of the function call you are currently writing. Very handy. By NoahFriedman.

Docs are from [MDN CSS reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)

## Screen Shots

![Alt text](ss0.png)

![Alt text](ss1.png)

## Usage

Use https://github.com/dimitri/el-get for an easy install, or put the css-eldoc somewhere in your load-path.

After aquiring the files, put the following in the your .emacs `(turn-on-css-eldoc)`


## Attention!

If your less mode's isearch became really slow, add the following code to your .emacs

```emacs-lisp
(defun isearch-forward-noeldoc ()
  "close eldoc temperaily"
  (interactive)
  (eldoc-mode -1)
  (isearch-forward)
  (eldoc-mode 1))
(add-hook 'less-css-mode-hook (lambda ()
				(local-set-key [remap isearch-forward] 'isearch-forward-noeldoc)))

(defun isearch-backward-noeldoc ()
  "close eldoc temperaily"
  (interactive)
  (eldoc-mode -1)
  (isearch-backward)
  (eldoc-mode 1))
(add-hook 'less-css-mode-hook (lambda ()
				(local-set-key [remap isearch-backward] 'isearch-backward-noeldoc)))
```
   
## License for DOC

Licensed under the Creative Commons Attribution-ShareAlike license (CC-BY-SA), v2.5 or any later version.

Copyright (C) [Mozilla Contributors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)

## License for Code

This software is licensed under the GPL v3

Copyright (C) 2012-2014 Zeno Zeng

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
