## D2Coding Nerd Font for Microsoft Windows

* 윈도우에서 한글 글꼴 너비와 아이콘 하단 쏠림 문제를 해결한 D2Coding Nerd Font 입니다.

    * Windows Terminal, Sublime Text에서 정상 출력됨을 확인하였습니다.
    * `D2CodingNFX`는 `D2Coding` 원본 폰트에서 한글 자간과 글폭을 수정한 버전입니다.
	* `gdi` 방식으로 폰트를 렌더링하는 클라이언트(Notepad 등)에서는 `D2CodingNFX`를 선택해야 자간이 정상 출력 됩니다.
    * `directdraw` 방식으로 폰트를 렌더링하는 클라이언트(Windows Terminal 등)에서는 `D2CodingNF`를 선택해야 자간이 정상 출력 됩니다.

* 기존 폰트를 제거하고 다음의 파일을 설치하면 됩니다. Regular와 Bold는 별도 파일입니다.

    * Regular: `D2CodingNF-Ver1.3.2-20180524.ttf`, `D2CodingNFX-Ver1.3.2-20180524.ttf`
    * Bold: `D2CodingNF-Bold-Ver1.3.2-20180524.ttf`, `D2CodingNFX-Bold-Ver1.3.2-20180524.ttf`

* 직접 제작하기 위해서는 다음과 같이 `patcher.py`를 사용합니다.

    * [Nerd Font 공식 저장소에 있는 patcher](https://github.com/ryanoasis/nerd-fonts/blob/master/font-patcher)에서 한글에 대한 예외 처리를 추가하였습니다.
    * `fontforge`가 설치 되어 있어야 합니다.
    * `--use-single-width-glyphs` 옵션을 추가해야 예외처리 됩니다.
    * WSL에서의 빌드를 권장합니다.
    * Bold는 `D2CodingBold-Ver1.3.2-20180524.ttf`로 같은 명령을 실행합니다. 패처가 패밀리 이름을 `D2CodingBoldNF`로 출력하므로, Regular와 같은 패밀리(`D2CodingNF`, `D2CodingNFX`)의 Bold로 이름을 바꾸고 글폭을 Regular에 맞춰야 합니다.

    ```bash
    apt install fontforge
    ```

    ```bash
    fontforge -script patcher.py "D2Coding-Ver1.3.2-20180524.ttf" --windows --complete --careful --postprocess --removeligatures --adjust-line-height --glyphdir "glyphs/" --outputdir "output/" --extension "ttf" --quiet --no-progressbars --use-single-width-glyphs
    ```
