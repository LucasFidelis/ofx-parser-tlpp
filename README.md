# OFX Parser TL++

OFX Parser TL++ is a TL++ library designed to parse a content from OFX File to Well Formed XML or a JSON string.

# Sample

```
#Include 'tlpp-object.th'
#Include 'tlpp-core.th'
#Include 'Protheus.ch'

User Function OFX2XML
    Private cOFXContent as Character
    cOFXContent := ReadFile('I://tmp/sampleofx.ofx') // <- Your file path here 

    ofxParser := OFXParser():New(cOFXContent)
    cXML := ofxParser:ToXML()
    CopyToClipboard(cXML)
Return .T.

Static Function ReadFile(cPath)
    Local oFile
    Local cFileContent := ''
    oFile := FWFileReader():New(cPath)
    If (oFile:Open())
        While (oFile:hasLine())
            cFileContent += oFile:GetLine()
        End
        oFile:Close()
    EndIf
Return cFileContent
```

## Todo

* Implement a method to JSON string.

## Disclaimer

This project is not associated, authorized, endorsed by, or in any way with TOTVS S/A.

TOTVS S/A, Protheus, ADVPL as well as related names, marks, emblems and images are registered trademarks of their respective owners.

## License

MIT License

Copyright (c) 2023 Lucas Fidélis

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.