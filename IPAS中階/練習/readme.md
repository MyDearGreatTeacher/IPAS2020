#
```
REG QUERY KeyName [/v [ValueName] | /ve] [/s]
          [/f Data [/k] [/d] [/c] [/e]] [/t Type] [/z] [/se Separator]
          [/reg:32 | /reg:64]

  KeyName  [\\Machine\]FullKey
           Machine - 遠端電腦的名稱 - 如果省略，預設是目前的電腦。對於遠端
                     電腦，僅能使用 HKLM 與 HKU
           FullKey - 格式為 ROOTKEY\SubKey  名稱
                ROOTKEY - [ HKLM | HKCU | HKCR | HKU | HKCC ]
                SubKey  - 所選取 ROOTKEY 之下的登錄機碼的完整 名稱

  /v       查詢特定登錄機碼值。
           如果省略，將查詢機碼的所有值。

           只有當此切換參數與 /f 切換參數搭配使用時，這個切換 參數的引數才
           能省略。這指定只在 ValueName 中搜尋。

  /ve      查詢預設值或空值名稱 (預設)。

  /s       遞迴查詢所有子機碼與值 (就像 dir /s)。

  /se      指定 REG_MULTI_SZ 資料字串的分隔符號 (長度僅限 1 個字元)。預設
           是使用 "\0" 做為分隔符號。

  /f       指定要搜尋的資料或模式。
           如果字串包含空白，請使用雙引號。預設是 "*"。

  /k       指定僅搜尋機碼名稱。

  /d       指定僅搜尋資料。

  /c       指定搜尋區分大小寫。
           預設搜尋是不區分大小寫。

  /e       指定只回傳完全相符的搜尋結果。
           根據預設，會傳回所有相符的搜尋結果。

  /t       指定登錄值資料類型。
           有效的類型為:
             REG_SZ、REG_MULTI_SZ、REG_EXPAND_SZ、
             REG_DWORD、REG_QWORD、REG_BINARY、REG_NONE
           預設為所有類型。

  /z       Verbose: 顯示 ValueName 類型的對應數值。

  /reg:32  指定應該使用 32 位元登錄檢視來存取機碼。

  /reg:64  指定應該使用 64 位元登錄檢視來存取機碼。

範例:

  REG QUERY HKLM\Software\Microsoft\ResKit /v Version
    顯示登錄值 Version 的值

  REG QUERY \\ABC\HKLM\Software\Microsoft\ResKit t\Setup /s
    顯示遠端電腦 ABC 中，登錄機碼 Setup 之下的所有子機碼與值

  REG QUERY HKLM\Software\Microsoft\ResKit t\Setup /se #
    顯示所有類型為 REG_MULTI_SZ，且使用 "#" 做為分隔符號之值名稱的所有機碼與值。

  REG QUERY HKLM /f SYSTEM /t REG_SZ /c /e
    顯示 HKLM 根目錄下，資料類型為 REG_SZ，且與 "SYSTEM" 完全 相符的機碼、值
    與資料 (區分大小寫)。

  REG QUERY HKCU /f 0F /d /t REG_BINARY
    顯示 HKCU 根目錄下，資料類型為 REG_BINARY，且資料包含 "0F" 的機碼、值與資料

  REG QUERY HKLM\SOFTWARE /ve
    顯示 HKLM\SOFTWARE 之下，空值 (預設) 的值與資料
```
