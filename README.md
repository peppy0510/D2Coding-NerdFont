## D2Coding Nerd Font

* 한글 글꼴 너비와 아이콘 하단 쏠림 문제를 해결한 D2Coding Nerd Font 입니다.

  * Notepad, Windows Terminal, Sublime Text (gdi, directwrite, ...) 등에서 정상 출력됨을 확인하였습니다.
  * 윈도우 폰트 목록에는 `D2Coding NF`로 표시되며 Windows Terminal이나 각종 IDE에서는 `D2Coding`으로 설정하면 됩니다.

* 기존 폰트를 제거하고 다음의 파일만 설치하면 됩니다.

  `D2Coding-Ver1.3.2-20180524-NF.ttf`

* 직접 제작하기 위해서는 다음과 같이 `patcher.py`를 사용합니다.

  * [Nerd Font 공식 저장소에 있는 patcher](https://github.com/ryanoasis/nerd-fonts/blob/master/font-patcher)에서 한글에 대한 예외 처리를 추가하였습니다.
  * `fontforge`가 설치 되어 있어야 합니다.
  * `--use-single-width-glyphs` 옵션을 추가해야 예외처리가 됩니다.
  
  ```bash
  apt install fontforge
  ```
  
  ```bash
  fontforge -script patcher.py "D2CodingBold-Ver1.3.2-20180524.ttf" --windows --complete --careful --postprocess --removeligatures --adjust-line-height --glyphdir "glyphs/" --outputdir "output/" --extension "ttf" --quiet --no-progressbars --use-single-width-glyphs
  ```
  
  

