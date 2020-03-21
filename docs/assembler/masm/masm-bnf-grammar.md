---
title: Microsoft 매크로 어셈블러 BNF 문법
description: X 64 용 MASM에 대 한 BNF 설명입니다.
ms.date: 12/17/2019
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), BNF reference
ms.openlocfilehash: 1a9577292e60db73838e5e6b850a4634db959fd6
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075460"
---
# <a name="microsoft-macro-assembler-bnf-grammar"></a>Microsoft 매크로 어셈블러 BNF 문법

이 페이지에는 MASM 문법에 대 한 BNF 설명이 포함 되어 있습니다. 이는 참조 항목에 대 한 보완으로 제공 되며 완전 하지 않을 수 있습니다. 키워드, 매개 변수, 작업 등에 대 한 자세한 내용은 참조 항목을 참조 하세요.

BNF를 사용 하는 방법을 보여 주기 위해 다음 다이어그램에서는 비터미널 *Typedefdir*부터 TYPEDEF 지시문의 정의를 보여 줍니다.

![MASM BNF 예제](media/bnf.png)

각 가로 중괄호 아래의 항목은 추가로 정의할 수 있는 터미널 (예: **NEAR16**, **NEAR32**, **FAR16**및 **FAR32**) 또는 비 터미널 (예: *한정자*, *qualifiedType*, *distance*및 *protoSpec*)입니다. *Typedefdir* 정의의 각 기울임꼴 비터미널 BNF의 항목 이기도 합니다. 3 개의 수직선은 비터미널에 대 한 분기 정의를 나타내므로이 그림에서는 간단한 설명을 위해 설명 하지 않습니다.

BNF 문법을 통해 재귀 정의를 사용할 수 있습니다. 예를 들어, 문법에서는 qualifiedType에 대 한 정의 구성 요소인 qualifiedType를 가능한 정의로 사용 합니다. "|" 기호는 대체 식 중에서 선택 항목을 지정 합니다 (예: *endOfLine* | *comment*). 이중 중괄호는 선택적 매개 변수를 지정 합니다 (예: ⟦ *macroParmList* ⟧). 대괄호는 실제로 소스 코드에 표시 되지 않습니다.

## <a name="masm-nonterminals"></a>MASM 비 터미널

*;;* \
&nbsp;&nbsp;&nbsp;&nbsp;*endOfLine* | *설명*

*= Dir*\
&nbsp;&nbsp;&nbsp;&nbsp;*id* = *immExpr* ;;

*Addop*\
&nbsp;&nbsp;&nbsp;&nbsp;+ | -

*Aexpr*\
&nbsp;&nbsp;&nbsp;&nbsp;*용어* | *aexpr* && *용어*

*Altid*\
&nbsp;&nbsp;&nbsp;&nbsp;*id*

*arbitraryText*\
&nbsp;&nbsp;&nbsp;&nbsp;*charList*

*asmInstruction*\
&nbsp;&nbsp;&nbsp;&nbsp;*니모닉* ⟦ *exprList* ⟧

*assumeDir*\
&nbsp;&nbsp; **&nbsp;&nbsp;** *assumeList* ; \
&nbsp;&nbsp;&nbsp;&nbsp;| **아무 것도 가정** 하지 않습니다.

*assumeList*\
&nbsp;&nbsp;&nbsp;&nbsp;*assumeRegister* | *assumeList* , *assumeRegister*\

*assumeReg*\
&nbsp;&nbsp;&nbsp;&nbsp;*등록* : *assumeVal*

*assumeRegister*\
&nbsp;&nbsp;&nbsp;&nbsp;*assumeSegReg* | *assumeReg*

*assumeSegReg*\
&nbsp;&nbsp;&nbsp;&nbsp;*segmentRegister* : *assumeSegVal*

*assumeSegVal*\
&nbsp;&nbsp;&nbsp;&nbsp;*프레임 식* | **NOTHING** | **오류**

*assumeVal*\
&nbsp;&nbsp;&nbsp;&nbsp;*qualifiedType* | **NOTHING** | **오류**

*bcdConst*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *sign* ⟧ *denumber*

*Binaryop*\
&nbsp;&nbsp;&nbsp;&nbsp;= = |! = | > = | < = | > | < | &

*Bitdef*\
&nbsp;&nbsp;&nbsp;&nbsp;*Bitfieldid* : *bitfieldid* ⟦ = *constExpr* ⟧

*Bitdeflist*\
&nbsp;&nbsp;&nbsp;&nbsp;*Bitdef* | *bitdeflist* , ⟦;; ⟧ *Bitdef*

*Bitfieldid*\
&nbsp;&nbsp;&nbsp;&nbsp;*id*

*Bitfieldsize*\
*constExpr* &nbsp;&nbsp;&nbsp;&nbsp;

*Blockstatements*\
&nbsp;&nbsp;&nbsp;&nbsp;*directiveList*\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. 계속** **합니다. IF** *cexpr* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **.** ⟦ **를 중단 합니다. IF** *cexpr* ⟧

*bool*\
&nbsp;&nbsp;&nbsp;&nbsp;**TRUE** | **FALSE**

*byteRegister*\
&nbsp;&nbsp;&nbsp;&nbsp;AL | AH | CL | CH | DL | DH | BL | BH | R8B | R9B | R10B | R11B | R12B | R13B | R14B | R15B

*Cexpr*\
&nbsp;&nbsp;&nbsp;&nbsp;*aexpr* | *Cexpr* || *aexpr*

*문자*\
&nbsp;&nbsp;&nbsp;는 줄 바꿈 (10)을 제외 하 고 0 ~ 255 범위에서 서 수를 포함 하는 모든 문자를 &nbsp;합니다.

*charList*\
&nbsp;&nbsp;&nbsp;&nbsp;*문자* | *charList* 문자

*className*\
&nbsp;&nbsp;&nbsp;&nbsp;*문자열*

*주석 decl*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *nearfar* ⟧ ⟦ *langType* ⟧ *id* : *주석 유형*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦: *constExpr* ⟧

*주석 디렉터리*\
&nbsp;&nbsp;&nbsp;&nbsp;**통신**\
&nbsp;&nbsp;&nbsp;&nbsp;*주석 목록* ;;

*주석*\
&nbsp;&nbsp;&nbsp;&nbsp;; *텍스트* ;;

*commentDir*\
&nbsp;&nbsp;&nbsp;**주석** *구분 기호* 를 &nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp;*텍스트*\
&nbsp;&nbsp;&nbsp;&nbsp;*텍스트* *구분 기호* *텍스트* ;;

*주석 목록*\
&nbsp;&nbsp;&nbsp;&nbsp;*주석* Decl | *주석 목록* , *주석 decl*

*주석 형식*\
&nbsp;&nbsp;&nbsp;&nbsp;*유형* | *constExpr*

*상수*\
&nbsp;&nbsp;&nbsp;&nbsp;*digits* ⟦ *radixOverride* ⟧

*constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;*expr*

*Contextdir*\
&nbsp;&nbsp;&nbsp;&nbsp;**Pushcontext** *contextitemlist* ; \
&nbsp;&nbsp;&nbsp;&nbsp;**POPCONTEXT** *contextitemlist* ;;

*Contextitem*\
&nbsp;&nbsp;&nbsp;&nbsp; | **CPU** | 모두 **나열** |  | **기** 하는 **것으로 가정** 합니다. **ALL**

*Contextitemlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*contextitem* | *contextitemlist* , *contextitem*

*Controlblock*\
&nbsp;&nbsp;&nbsp;&nbsp;*whileBlock* | *repeatblock*

*Controldir*\
&nbsp;&nbsp;&nbsp;&nbsp;*controlIf* | *controlblock*

*Controlelseif*\
&nbsp;&nbsp;&nbsp;&nbsp; **. ELSEIF** &nbsp;&nbsp;&nbsp;&nbsp;*cexpr* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*directiveList* \
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Controlelseif* ⟧

*controlIf*\
&nbsp;&nbsp;&nbsp;&nbsp; **. &nbsp;&nbsp;** &nbsp;&nbsp;*cexpr* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*directiveList*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Controlelseif* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦ **. ELSE** ;; \
&nbsp;&nbsp;&nbsp;&nbsp;[*directiveList*⟧ \
&nbsp;&nbsp;&nbsp;&nbsp; **. ENDIF** ;;

*보조 프로세서*\
&nbsp;&nbsp;&nbsp;&nbsp;. 8087 | 287 |. 387 |. NO87

*Crefdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Crefoption* ;;

*Crefoption*\
&nbsp;&nbsp;&nbsp;&nbsp; **. CREF**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. XCREF** ⟦ *idlist* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. NOCREF** ⟦ *idlist* ⟧

*Cxzexpr*\
&nbsp;&nbsp;&nbsp;&nbsp;*expr*\
&nbsp;&nbsp;&nbsp;&nbsp;|! *expr*\
&nbsp;&nbsp;&nbsp;&nbsp;| *expr* = = expr \
&nbsp;&nbsp;&nbsp;&nbsp;| *expr* ! = expr

*Datadecl*\
&nbsp;&nbsp;&nbsp;&nbsp;DB | DW | DD | DF | DQ | DT | *dataType* | *typeId*

*Datadir*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *id* ⟧ *dataItem* ;;

*dataItem*\
&nbsp;&nbsp;&nbsp;&nbsp;*Datadecl* *scalarInstList*\
&nbsp;&nbsp;&nbsp;&nbsp;| *structTag* *structInstList*\
&nbsp;&nbsp;&nbsp;&nbsp;| *typeId* *structInstList*\
&nbsp;&nbsp;&nbsp;&nbsp;| *unionTag* *structInstList*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Recordtag* *recordtag 목록*

*데이터 형식*\
&nbsp;&nbsp;&nbsp;&nbsp;바이트 | SBYTE | WORD | 검 | DWORD | SDWORD | FWORD | QWORD(64 | SQWORD | 1TB | OWORD | REAL4 | REAL8 | REAL10 | MMWORD | XMMWORD | YMMWORD

*\*
&nbsp;&nbsp;&nbsp;&nbsp;0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 되었는지

\ *수*
&nbsp;&nbsp; *&nbsp;&nbsp;\*
&nbsp;&nbsp;&nbsp;&nbsp;| *바이트 수* *decdigit*

*구분 기호*\
*whiteSpaceCharacter* 를 제외한 모든 문자를 &nbsp;&nbsp;&nbsp;&nbsp;

*숫자*\
&nbsp;&nbsp; *&nbsp;&nbsp;\*
&nbsp;&nbsp;&nbsp;&nbsp;| *자리 숫자* *\*
&nbsp;&nbsp;&nbsp;&nbsp;| *숫자* hexdigit

*지시문*\
&nbsp;&nbsp;&nbsp;&nbsp;*일반 dir* | *segmentDef*

*directiveList*\
&nbsp;&nbsp;&nbsp;&nbsp;*지시문* | *directiveList* *지시문*

*거리*\
&nbsp;&nbsp;&nbsp;&nbsp;*nearfar* | **NEAR16** | **NEAR32** | **FAR16** | **FAR32**

*e 01,* \
&nbsp;&nbsp;&nbsp;&nbsp;e 01, *Orop* *e02* | *e02*

*e02*\
&nbsp;&nbsp;&nbsp;&nbsp;e02 **및** *e03* | *e03*

*e03*\
&nbsp;&nbsp; **&nbsp;&nbsp;** *e04* | *e04*

*e04*\
&nbsp;&nbsp;&nbsp;&nbsp;*e04* *relop* *e05* | *e05*

*e05*\
&nbsp;&nbsp;&nbsp;&nbsp;*e05* *addop* *e06* | *e06*

*e06*\
&nbsp;&nbsp;&nbsp;&nbsp;*e06* *mulOp* *e07* | *e06* *shiftOp* *e07* | *e07*

*e07*\
&nbsp;&nbsp;&nbsp;&nbsp;*e07* *addop* *e08* | *e08*

*e08*\
&nbsp;&nbsp;&nbsp;&nbsp;**HIGH** *e09*\
&nbsp;&nbsp;&nbsp;&nbsp;| **LOW** *e09*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Highword** *e09*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Lowword** *e09*\
&nbsp;&nbsp;&nbsp;&nbsp;| *e09*

*e09*\
&nbsp;&nbsp;&nbsp;&nbsp;**OFFSET** *e10*\
&nbsp;&nbsp;&nbsp;&nbsp;| **SEG** *e10*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Lroffset** *e10*\
&nbsp;&nbsp;&nbsp;&nbsp;| **TYPE** *e10*\
&nbsp;&nbsp;&nbsp;&nbsp;**이** *e10* | \
&nbsp;&nbsp;&nbsp;&nbsp;| *e09* **PTR** *e10*\
&nbsp;&nbsp;&nbsp;&nbsp;| *e09* : *e10*\
&nbsp;&nbsp;&nbsp;&nbsp;| *e10*

*e10*\
&nbsp;&nbsp;&nbsp;&nbsp;*e10* . *e11*\
&nbsp;&nbsp;&nbsp;&nbsp;| *e10* ⟦ *expr* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| *e11*

*e11*\
&nbsp;&nbsp;&nbsp;&nbsp;( *expr* ) \
&nbsp;&nbsp;&nbsp;&nbsp;| ⟦ *expr* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| **너비** *id*\
&nbsp;&nbsp;&nbsp;&nbsp;| **마스크** *id*\
&nbsp;&nbsp;&nbsp;&nbsp;| **크기** *sizeArg*\
&nbsp;&nbsp;&nbsp;&nbsp;| **SIZEOF** *sizeArg*\
&nbsp;&nbsp;&nbsp;&nbsp;| **길이** *id*\
&nbsp;&nbsp;&nbsp;&nbsp;| **LENGTHOF** *id*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Recordconst*\
&nbsp;&nbsp;&nbsp;&nbsp;| *문자열*\
&nbsp;&nbsp;&nbsp;&nbsp;| *상수*\
&nbsp;&nbsp;&nbsp;&nbsp;| *형식*\
&nbsp;&nbsp;&nbsp;&nbsp;| *id*\
&nbsp;&nbsp;&nbsp;&nbsp;| **$**\
&nbsp;&nbsp;&nbsp;&nbsp;| *segmentRegister*\
&nbsp;&nbsp;&nbsp;&nbsp;| *등록*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ST**\
&nbsp;&nbsp;&nbsp;&nbsp;| **ST** ( *expr* )

*echoDir*\
&nbsp;&nbsp;&nbsp;&nbsp;**에코**\
&nbsp;&nbsp;&nbsp;&nbsp;*arbitraryText* ;; \
%**OUT** *arbitraryText* ;; \

*elseifBlock*\
&nbsp;&nbsp;&nbsp;&nbsp;*elseifStatement* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*directiveList*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *elseifBlock* ⟧ \

*elseifStatement*\
&nbsp;&nbsp;&nbsp;&nbsp;**ELSEIF** *constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIFE** *constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIFB** *textitem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIFNB** *textitem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIFDEF** *id*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIFNDEF** *id*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIFDIF** *textitem* , *textitem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIFDIFI** *textitem* , *textitem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIFIDN** *textitem* , *textitem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIFIDNI** *textitem* , *textitem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIF1**\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIF2**

*Enddir*\
&nbsp;&nbsp;&nbsp;&nbsp;**END** ⟦ *immExpr* ⟧;;

*Endpdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Procid* **endp** ;;

*Endsdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*id가* **끝남** ;;

*\*
&nbsp;&nbsp;&nbsp;&nbsp;*textMacroId* **같음** *equType* ;;

*equType*\
&nbsp;&nbsp;&nbsp;&nbsp;*immExpr* | *textliteral*

*Errordir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Erroropt* ;;

*Erroropt*\
&nbsp;&nbsp;&nbsp;&nbsp; **. ERR** ⟦ *textitem* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRE** *constExpr* ⟦ *optText* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRNZ** *constExpr* ⟦ *optText* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRB** *textitem* ⟦ *optText* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRNB** *textitem* ⟦ *optText* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRDEF** *id* ⟦ *optText* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. .ERRNDEF** *id* ⟦ *optText* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. .ERRDIF** *textitem* , *textitem* ⟦ *optText* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRDIFI** *textitem* , *textitem* ⟦ *optText* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRIDN** *textitem* , *textitem* ⟦ *optText* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRIDNI** *textitem* , *textitem* ⟦ *optText* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERR1** ⟦ *textitem* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. .ERR2** ⟦ *textitem* ⟧

*Exitdir*\
&nbsp;&nbsp;&nbsp;&nbsp; **. EXIT** &nbsp;&nbsp;&nbsp;&nbsp;⟦ *expr* ⟧;;

*exitmDir*\
&nbsp;&nbsp;&nbsp;&nbsp;: EXITM | EXITM *Textitem*

*지* 수\
&nbsp;&nbsp;&nbsp;&nbsp;E ⟦ *sign* ⟧ *denumber*

*expr*\
&nbsp;&nbsp;&nbsp;&nbsp;**SHORT** *e05*\
&nbsp;&nbsp;&nbsp;&nbsp;|  **.** E 01, \ 형식
&nbsp;&nbsp;&nbsp;&nbsp;| **Opattr** *e 01,* \
&nbsp;&nbsp;&nbsp;&nbsp;| *e 01,*

*exprList*\
&nbsp;&nbsp;&nbsp;&nbsp;*expr* | *exprList* , *expr*

*externDef*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *langType* ⟧ *Id* ⟦ ( *Altid* ) ⟧: *externType*

*externDir*\
&nbsp;&nbsp;&nbsp;&nbsp;*externKey* *externList* ;;

*externKey*\
&nbsp;&nbsp;&nbsp;&nbsp;**Extrn** | **EXTERN** | **EXTERNDEF**

*externList*\
&nbsp;&nbsp;&nbsp;&nbsp;*externDef* | *externList* , ⟦;; ⟧ *externDef*

*externType*\
&nbsp;&nbsp;&nbsp;&nbsp;**ABS** | *qualifiedType*

*Fieldalign*\
*constExpr* &nbsp;&nbsp;&nbsp;&nbsp;

*fieldInit*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Initvalue* ⟧ | *structInstance*

*Fieldinitlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*fieldInit* | *fieldinitlist* , ⟦;; ⟧ *fieldInit*

*fileChar*\
&nbsp;&nbsp;&nbsp;&nbsp;*구분 기호*

*fileCharList*\
&nbsp;&nbsp;&nbsp;&nbsp;*fileChar* | *fileCharList* *fileChar*

*fileSpec*\
&nbsp;&nbsp;&nbsp;&nbsp;*fileCharList* | *textliteral*

*플래그 이름*\
&nbsp;&nbsp;&nbsp;&nbsp;**0 입니까?** | **수행 하 시겠습니까?****오버플로  | ?** | **기호**패리티를  | **하 시겠습니까?**

*floatNumber*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *sign* ⟧ *denumber* . ⟦ *Denumber* ⟧ ⟦ *지* 수 ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| *숫자* R | *숫자* r

*forcDir*\
&nbsp;&nbsp;&nbsp;&nbsp;**Forc** | **irpc**

*Fordir*\
 | **IRP** **에 대 한** &nbsp;&nbsp;&nbsp;&nbsp;

*forParm*\
&nbsp;&nbsp;&nbsp;&nbsp;*id* ⟦: *forParmType* ⟧

*forParmType*\
&nbsp;&nbsp;&nbsp;&nbsp;**요청** | = *Textliteral*

*fpuRegister*\
&nbsp;&nbsp;&nbsp;&nbsp;**ST** *식*

*프레임 식*\
&nbsp;&nbsp;&nbsp;&nbsp;**SEG** *id*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Idgroup** : *id*\
&nbsp;&nbsp;&nbsp;&nbsp;| *segmentRegister* : *id*\
&nbsp;&nbsp;&nbsp;&nbsp;| *id*

*일반 디렉터리*\
&nbsp;&nbsp;&nbsp;&nbsp;*Modeldir* | *SegOrderDir* | *namedir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *includeLibDir* | *commentDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Groupdir* | *assumeDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *structDir* | *Recorddir* | *typedefdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *externDir* | *Publicdir* | *protoTypeDir* * | \*
&nbsp;&nbsp;&nbsp; *&nbsp;| * = Dir | *Textdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Contextdir* | *dir* | *processorDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *radixDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *titleDir* | *Pagedir* | *listdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Crefdir* | *echoDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Ifdir* | *Errordir* | *includedir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *macroDir* | *macroCall* | *macroRepeat* | *purgeDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *macroWhile* | *macroFor* | *macroForc*\
&nbsp;&nbsp;&nbsp;&nbsp;| *aliasDir*

*gpRegister*\
&nbsp;&nbsp;&nbsp;&nbsp;AX | EAX | CX | ECX | DX | EDX | BX | EBX | DI | EDI | SI | ESI | BP | EBP | SP | ESP | RSP | R8W | R8D | R9W | R9D | R12D | R13W | R13D | R14W | R14D

*Groupdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*groupId* **그룹** *segIdList*

*groupId*\
&nbsp;&nbsp;&nbsp;&nbsp;*id*

*hexdigit*\
&nbsp;&nbsp;&nbsp;&nbsp;a | b | c | d | e | f | A | B | C | D | E | 350

*id*\
식별자의 첫 번째 문자를 &nbsp;&nbsp;&nbsp;대문자 (`[A–Za-z]`) 또는 이러한 네 문자 중 하나를 사용할 수 있습니다. 나머지 문자는 같은 문자 또는 10 진수 (`@ _ $ ?`)를 사용할 수 있습니다. &nbsp;`[0–9]` 최대 길이는 247 자입니다.

*Idlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*id* | *idlist* , *id*

*Ifdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Ifstatement* ; \
&nbsp;&nbsp;&nbsp;&nbsp;*directiveList*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *elseifBlock* ⟧ \
&nbsp;&nbsp;&nbsp; **&nbsp;⟦;;** \
&nbsp;&nbsp;&nbsp;&nbsp;*directiveList* ⟧;; \

*Ifstatement*\
*constExpr* 을 &nbsp;&nbsp; **&nbsp;&nbsp;\**
&nbsp;&nbsp;&nbsp;&nbsp;| **Ife** *constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| **IFB** *textitem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Ifnb** *textitem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **IFDEF** *id*\
&nbsp;&nbsp;&nbsp;&nbsp;| **IFNDEF** *id*\
&nbsp;&nbsp;&nbsp;&nbsp;| **IFDIF** *textitem* , *textitem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Ifdifi** *textitem* , *textitem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Ifidn** *textitem* , *textitem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Ifidni** *textitem* , *textitem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **IF1**\
&nbsp;&nbsp;&nbsp;&nbsp;| **IF2**

*immExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;*expr*

*Includedir*\
&nbsp;&nbsp;&nbsp;&nbsp;에 **는** *fileSpec* 이 포함 됩니다.

*includeLibDir*\
&nbsp;&nbsp;&nbsp;&nbsp;**INCLUDELIB** *fileSpec* ;;

*Initvalue*\
&nbsp;&nbsp;&nbsp;&nbsp;*immExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| *문자열*\
&nbsp;&nbsp;&nbsp;&nbsp;|? \
&nbsp;&nbsp;&nbsp;&nbsp;| *constExpr* **DUP** ( *scalarInstList* ) \
&nbsp;&nbsp;&nbsp;&nbsp;| *floatNumber*\
&nbsp;&nbsp;&nbsp;&nbsp;| *bcdConst*

*inSegDir*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Labeldef* ⟧ *inSegmentDir*

*inSegDirList*\
&nbsp;&nbsp;&nbsp;&nbsp;*inSegDir* | *inSegDirList* *inSegDir*

*inSegmentDir*\
&nbsp;&nbsp;&nbsp;&nbsp;*명령*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Datadir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Controldir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Startupdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Exitdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *offsetDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Labeldir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Procdir* ⟦ *localdirlist* ⟧ ⟦ *inSegDirList* ⟧ *endpdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *invokeDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *일반 디렉터리*

*instrPrefix*\
&nbsp;&nbsp; **&nbsp;&nbsp; | ** **Repe** | **REPZ** | **Repne** | **repnz** | **잠금**

*명령*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *instrPrefix* ⟧ *asmInstruction*

*invokeArg*\
&nbsp;&nbsp;&nbsp;&nbsp;*register* :: *register* | *expr* | **ADDR** *expr*

*invokeDir*\
&nbsp;&nbsp; **&nbsp;&nbsp;** *expr* ⟦, ⟦;; ⟧ *invokeList* ⟧;;

*invokeList*\
&nbsp;&nbsp;&nbsp;&nbsp;*invokeArg* | *invokeList* , ⟦;; ⟧ *invokeArg*

*키워드*\
모든 예약어를 &nbsp;&nbsp;&nbsp;&nbsp;합니다.

*Keywordlist* 아래\
&nbsp;&nbsp;&nbsp;&nbsp;*키워드* | *키워드* *keywordlist* 모음

*Labeldef*\
&nbsp;&nbsp;&nbsp;&nbsp;*id* : | *id* :: | @@:

*Labeldir*\
&nbsp;&nbsp;&nbsp;&nbsp;*id* **레이블** *qualifiedType* ;;

*langType*\
&nbsp;&nbsp;&nbsp;&nbsp;**C** | **파스칼** | **포트란** | **BASIC** | **SYSCALL** | **STDCALL**

*Listdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Listoption* ;;

*Listoption*\
&nbsp;&nbsp;&nbsp;&nbsp; **. 목록**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. NOLIST**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. XLIST**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. LISTALL**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. .LISTIF**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. .LFCOND**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. .NOLISTIF**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. SFST\**
&nbsp;&nbsp;&nbsp;&nbsp;|  **. .TFCOND**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. .LISTMACROALL** |  **. LALL**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. NOLISTMACRO** | **입니다. .SALL**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. LISTMACRO** | **입니다. XALL**\

*Localdef*\
&nbsp;&nbsp;&nbsp;&nbsp;**로컬** *idlist* ;;

*Localdir*\
&nbsp;&nbsp;&nbsp;&nbsp;**로컬** *parmlist* ;;

*Localdirlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*localdir* | *localtlist* *localdir*

*Locallist*\
&nbsp;&nbsp;&nbsp;&nbsp;*localdef* | *localdef 목록* *localDef*

*macroArg*\
 % *constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| %*textMacroId*\
&nbsp;&nbsp;&nbsp;&nbsp;| %*macroFuncId* ( *macroArgList* ) \
&nbsp;&nbsp;&nbsp;&nbsp;| *문자열*\
&nbsp;&nbsp;&nbsp;&nbsp;| *arbitraryText*\
&nbsp;&nbsp;&nbsp;&nbsp;| < *arbitraryText* >

*macroArgList*\
&nbsp;&nbsp;&nbsp;&nbsp;*macroArg* | *macroArgList* , *macroArg*

*macroBody*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Locallist* ⟧ *macroStmtList*

*macroCall*\
&nbsp;&nbsp;&nbsp;&nbsp;*id* *macroArgList* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;| *id* ( *macroArgList* )

*macroDir*\
&nbsp;&nbsp;&nbsp;&nbsp;*id* **매크로** ⟦ *macroParmList* ⟧;; \
&nbsp;&nbsp;&nbsp;&nbsp;*macroBody*\
&nbsp;&nbsp;&nbsp;&nbsp;**Endm** ;;

*macroFor*\
&nbsp;&nbsp;&nbsp;&nbsp;*Fordir* *ForParm* , < *macroArgList* >;; \
&nbsp;&nbsp;&nbsp;&nbsp;*macroBody*\
&nbsp;&nbsp;&nbsp;&nbsp;**Endm** ;;

*macroForc*\
&nbsp;&nbsp;&nbsp;&nbsp;*forcDir* *id* , *textliteral* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*macroBody*\
&nbsp;&nbsp;&nbsp;&nbsp;**Endm** ;;

*macroFuncId*\
&nbsp;&nbsp;&nbsp;&nbsp;*id*

*macroId*\
&nbsp;&nbsp;&nbsp;&nbsp;*macroProcId* | *macroFuncId*

*macroIdList*\
&nbsp;&nbsp;&nbsp;&nbsp;*macroId* | *macroIdList* , *macroId*

*macroLabel*\
&nbsp;&nbsp;&nbsp;&nbsp;*id*

*macroParm*\
&nbsp;&nbsp;&nbsp;&nbsp;*id* ⟦: *parmType* ⟧

*macroParmList*\
&nbsp;&nbsp;&nbsp;&nbsp;*macroParm* | *macroParmList* , ⟦;; ⟧ *macroParm*

*macroProcId*\
&nbsp;&nbsp;&nbsp;&nbsp;*id*

*macroRepeat*\
&nbsp;&nbsp;&nbsp;&nbsp;*Repeatdir* *constExpr* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*macroBody*\
&nbsp;&nbsp;&nbsp;&nbsp;**Endm** ;;

*macroStmt*\
&nbsp;&nbsp;&nbsp;&nbsp;*지시문* 을 \
&nbsp;&nbsp;&nbsp;&nbsp;| *exitmDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| : *macroLabel*\
&nbsp;&nbsp;&nbsp;&nbsp;| **GOTO**\
&nbsp;&nbsp;&nbsp;&nbsp;*macroLabel*

*macroStmtList*\
&nbsp;&nbsp;&nbsp;&nbsp;*macroStmt* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;| *macroStmtList* *macroStmt* ;; \

*macroWhile*\
*constExpr* 에 &nbsp;&nbsp; **&nbsp;&nbsp;;** \
&nbsp;&nbsp;&nbsp;&nbsp;*macroBody*\
&nbsp;&nbsp;&nbsp;&nbsp;**Endm** ;;

*Maptype*\
&nbsp;&nbsp;&nbsp;&nbsp;**모든** | **없음** | **NOTPUBLIC**

*Memoption*\
&nbsp;&nbsp; **&nbsp;&nbsp;작은** | **SMALL** | **MEDIUM** | **COMPACT** | **큰** |  ** | ** **FLAT**

*니모닉*\
&nbsp;&nbsp;&nbsp;&nbsp;명령 이름입니다.

*Modeldir*\
&nbsp;&nbsp;&nbsp;&nbsp; **. 모델**\
&nbsp;&nbsp;&nbsp;&nbsp;*Memoption* ⟦, *Modeloptlist* ⟧;;

*Modelopt*\
&nbsp;&nbsp;&nbsp;&nbsp;*langType* | *stackoption*

*Modeloptlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*modelopt* | *Modeloptlist* , *modelopt*

*모듈*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *directiveList* ⟧ *enddir*

*mulOp*\
&nbsp;&nbsp;&nbsp;&nbsp;\* | / | **MOD**

*Namedir*\
&nbsp;&nbsp;&nbsp;&nbsp;**이름**\
&nbsp;&nbsp;&nbsp;&nbsp;*id* ;; \

*nearfar*\
&nbsp;&nbsp;&nbsp;&nbsp;**근처** | **FAR**

*nestedStruct*\
&nbsp;&nbsp;&nbsp;&nbsp;*structHdr* ⟦ *id* ⟧;; \
&nbsp;&nbsp;&nbsp;&nbsp;*structBody*\
&nbsp;&nbsp;&nbsp;&nbsp;**종료** ; \

*offsetDir*\
&nbsp;&nbsp;&nbsp;&nbsp;*offsetDirType* ;;

*offsetDirType*\
&nbsp;&nbsp; **&nbsp;&nbsp; | ** **ORG** *immExpr* | **ALIGN** ⟦ *constExpr* ⟧

*offsetType*\
&nbsp;&nbsp;&nbsp;&nbsp;**그룹** | **세그먼트** | **FLAT**

*oldRecordFieldList*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *constExpr* ⟧ | *oldRecordFieldList* , ⟦ *constExpr* ⟧

기타 *dir*\
&nbsp;&nbsp;&nbsp;&nbsp;**옵션 옵션** *목록* ;;

*항목 항목*\
&nbsp;&nbsp;&nbsp;&nbsp;**CASEMAP** : *maptype*\
&nbsp;&nbsp;&nbsp;&nbsp;| **DOTNAME** | **NODOTNAME**\
&nbsp;&nbsp;&nbsp;&nbsp;| **에뮬레이터** | **noemulator**\
&nbsp;&nbsp;&nbsp;&nbsp;| **에필로그** : *macroId*\
&nbsp;&nbsp;&nbsp;&nbsp;| **EXPR16** | **EXPR32**\
&nbsp;&nbsp;&nbsp;&nbsp;| **언어** : *langType*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Ljmp**
| **noljmp**\
&nbsp;&nbsp;&nbsp;&nbsp;| **M510** | **NOM510**\
&nbsp;&nbsp;&nbsp;&nbsp;| **Nokeyword** : < *keywordlist* 모음 >\
&nbsp;&nbsp;&nbsp;&nbsp;| **Nosignextend**\
&nbsp;&nbsp;&nbsp;&nbsp;| **오프셋** : *offsetType*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Oldmacros** | **nooldmacros**\
&nbsp;&nbsp;&nbsp;&nbsp;| **Oldstructs** | **nooldstructs**\
&nbsp;&nbsp;&nbsp;&nbsp;| **PROC** : *ovisibility*\
&nbsp;&nbsp;&nbsp;&nbsp;| **프롤로그** : *macroId*\
&nbsp;&nbsp;&nbsp;&nbsp;| **READONLY** | **NOREADONLY**\
&nbsp;&nbsp;&nbsp;&nbsp;| **범위** | **noscoped** 지정 된\
&nbsp;&nbsp;&nbsp;&nbsp;| **세그먼트** : *segSize*\
&nbsp;&nbsp;&nbsp;&nbsp;| **SETIF2** : bool

\ *목록* (영문)
&nbsp;&nbsp;&nbsp;&nbsp;*항목* * | ;* ⟦;; ⟧; *항목*

*optText*\
&nbsp;&nbsp;&nbsp;&nbsp;, *Textitem*

*Orop*\
&nbsp;&nbsp;&nbsp;&nbsp;**또는** | **XOR**

*Ovisibility*\
&nbsp;&nbsp;&nbsp;&nbsp;**공용** | **개인** | **내보내기**

*Pagedir*\
&nbsp;&nbsp;&nbsp;&nbsp;**페이지** ⟦ *pageexpr* ⟧;;

*Pageexpr*\
&nbsp;&nbsp;&nbsp;&nbsp;\+ | ⟦ *pageLength* ⟧ ⟦, *pagewidth* ⟧

*pageLength*\
*constExpr* &nbsp;&nbsp;&nbsp;&nbsp;

*Pagewidth*\
*constExpr* &nbsp;&nbsp;&nbsp;&nbsp;

*parm*\
&nbsp;&nbsp;&nbsp;&nbsp;*Parmid* ⟦: *qualifiedType* ⟧ | *Parmid* ⟦ *constExpr* ⟧ ⟦: *qualifiedType* ⟧

*Parmid*\
&nbsp;&nbsp;&nbsp;&nbsp;*id*

*Parmlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*parm* | *parmlist* , ⟦;; ⟧ *parm*

*parmType*\
&nbsp;&nbsp;&nbsp;&nbsp;**요청** | = *Textliteral* | **VARARG**

*Poptions*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *distance* ⟧ ⟦ *LangType* ⟧ ⟦ *ovisibility* ⟧

*기본*\
&nbsp;&nbsp;&nbsp;&nbsp;*expr* *Binaryop* *expr* | *플래그 이름* | *expr*

*Procdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Procid* **프로시저**\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Poptions* ⟧ ⟦ < *macroArgList* > ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Usesregs* ⟧ ⟦ *Procparmlist* ⟧

*프로세서*\
&nbsp;&nbsp;&nbsp;&nbsp;|. 386 |. 386p |. 486 |. .486P \
&nbsp;&nbsp;&nbsp;&nbsp;|. 586 |. 586P |. 686 |. 686P |. 387

*processorDir*\
&nbsp;&nbsp;&nbsp;&nbsp;*프로세서* ; \
&nbsp;&nbsp;&nbsp;&nbsp;| *보조 프로세서* ;;

*Procid*\
&nbsp;&nbsp;&nbsp;&nbsp;*id*

*Procitem*\
&nbsp;&nbsp;&nbsp;&nbsp;*instrPrefix* | *Datadir* | *Labeldir* | *offsetDir* | *일반 디렉터리*

*Procparmlist*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦, ⟦;; ⟧ *Parmlist* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦, ⟦;; ⟧ *Parmid* : VARARG ⟧

*protoArg*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *id* ⟧: *qualifiedType*

*protoArgList*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦, ⟦;; ⟧ *protoList* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦, ⟦;; ⟧ ⟦ *id* ⟧: VARARG ⟧

*protoList*\
&nbsp;&nbsp;&nbsp;&nbsp;*protoArg*\
&nbsp;&nbsp;&nbsp;&nbsp;| *protoList* , ⟦;; ⟧ *protoArg*

*protoSpec*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *distance* ⟧ ⟦ *LangType* ⟧ ⟦ *protoArgList* ⟧ | *typeId*

*protoTypeDir*\
&nbsp;&nbsp;&nbsp;&nbsp;*id* **프로토콜** *protoSpec*

*Pubdef*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *langType* ⟧ *id*

*Publicdir*\
&nbsp;&nbsp;&nbsp;&nbsp;**공용** *publist* ;;

*Publist*\
&nbsp;&nbsp;&nbsp;&nbsp;*Pubdef* | *pubdef* , ⟦;; ⟧ *Pubdef*

*purgeDir*\
&nbsp;&nbsp;&nbsp;&nbsp;**PURGE** *macroIdList* 제거

*qualifiedType*\
&nbsp;&nbsp;&nbsp;&nbsp;*유형* | ⟦ *distance* ⟧ **PTR** ⟦ *qualifiedType* ⟧

*한정자*\
&nbsp;&nbsp;&nbsp;&nbsp;*qualifiedType* | **프로토콜** *protoSpec*

*견적*\
&nbsp;&nbsp;&nbsp;&nbsp;"| '

*Qwordregister*\
&nbsp;&nbsp;&nbsp;&nbsp;RAX | RCX | RDX | RBX | RDI | RSI | RBP | R8 | R 9 | R10 | R 11 | R12 | R13 | R14 | R15

*radixDir*\
&nbsp;&nbsp;&nbsp;&nbsp; **. 기** 하 방법 *constExpr* ;;

*radixOverride*\
&nbsp;&nbsp;&nbsp;&nbsp;h | o | q | t | y | H | O | Q | T | X.y

*Recordconst*\
&nbsp;&nbsp;&nbsp;&nbsp;*Recordtag* { *oldRecordFieldList* } | *oldRecordFieldList* > < *recordtag*

*Recorddir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Recordtag* **레코드** *bitdeflist* ;;

*recordFieldList*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *constExpr* ⟧ | *recordFieldList* , ⟦;; ⟧ ⟦ *constExpr* ⟧

*Recordinstance*\
 {⟦;; ⟧ *recordFieldList* ⟦;; ⟧} \
&nbsp;&nbsp;&nbsp;&nbsp;| < *oldRecordFieldList* >\
&nbsp;&nbsp;&nbsp;&nbsp;| *constExpr* **DUP** ( *recordinstance* )

\ *Recordlist*
&nbsp;&nbsp;&nbsp;&nbsp;*Recordinstance* | *recordinstance* ;; ⟧ *Recordinstance*

*Recordtag*\
&nbsp;&nbsp;&nbsp;&nbsp;*id*

\ *등록*
&nbsp;&nbsp;&nbsp;&nbsp;*specialRegister* | *gpRegister* | *byteRegister* | *Qwordregister* |  *fpuRegister* | *SIMDRegister* *segmentRegister | *

*Reglist*\
&nbsp;&nbsp; *&nbsp;&nbsp;등록* | *reglist* *등록*

*Relop*\
&nbsp;&nbsp;&nbsp;&nbsp;EQ | NE | LT | LE | GT | GE

*Repeatblock*\
&nbsp;&nbsp;&nbsp;&nbsp; **. 반복** ; \
&nbsp;&nbsp;&nbsp;&nbsp;*Blockstatements* ;; untilDir ;;

*Repeatdir*\
&nbsp;&nbsp;&nbsp;&nbsp;**반복** | **REPT**

*scalarInstList*\
&nbsp;&nbsp;&nbsp;&nbsp;*Initvalue* | *scalarInstList* , ⟦;; ⟧ *Initvalue*

*segAlign*\
&nbsp;&nbsp;&nbsp;&nbsp;**바이트** | **WORD** |  ** | **  | **PARA** **페이지**

*segAttrib*\
&nbsp;&nbsp;&nbsp;&nbsp;**공용** | **스택** * |  | * **에서** **PRIVATE** **일반적인** | **메모리** | 

*segDir*\
&nbsp;&nbsp;&nbsp;&nbsp; **. 코드**\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *segId* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. 데이터**\
&nbsp;&nbsp;&nbsp;&nbsp;|   **. 데이터?** \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. CONST**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. FARDATA**⟦ *segId* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|   **. FARDATA?** ⟦ *segId* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. STACK** ⟦ *constExpr* ⟧

*segId*\
&nbsp;&nbsp;&nbsp;&nbsp;*id*

*segIdList*\
&nbsp;&nbsp;&nbsp;&nbsp;*segId*\
&nbsp;&nbsp;&nbsp;&nbsp;| *segIdList* , *segId*

*segmentDef*\
&nbsp;&nbsp;&nbsp;&nbsp;*segmentDir* ⟦ *inSegDirList* ⟧ *endsdir* | *SimpleSegDir* ⟦ *inSegDirList ⟧* ⟦ *endsdir* ⟧

*segmentDir*\
&nbsp;&nbsp;&nbsp;&nbsp;*segId* **SEGMENT** ⟦ *segOptionList* ⟧;;

*segmentRegister*\
&nbsp;&nbsp;&nbsp;&nbsp;**CS** | **DS** | **ES** | **FS** | **GS** | **SS**

*segOption*\
&nbsp;&nbsp;&nbsp;&nbsp;*segAlign*\
&nbsp;&nbsp;&nbsp;&nbsp;| *segRO*\
&nbsp;&nbsp;&nbsp;&nbsp;| *segAttrib*\
&nbsp;&nbsp;&nbsp;&nbsp;| *segSize*\
&nbsp;&nbsp;&nbsp;&nbsp;| *className*

*segOptionList*\
&nbsp;&nbsp;&nbsp;&nbsp;*segOption* | *segOptionList* *segOption*

*segOrderDir*\
&nbsp;&nbsp;&nbsp;&nbsp; **. 알파** | **입니다. SEQ** | **입니다. .DOSSEG** |  **.dosseg**

*segRO*\
**읽기 전용** &nbsp;&nbsp;&nbsp;&nbsp;

*segSize*\
&nbsp;&nbsp;&nbsp;&nbsp;**USE16** | **USE32** | **FLAT**

*shiftOp*\
&nbsp;&nbsp;&nbsp;&nbsp;**SHR** | **SHL**

*서명*\
 - | +

*\*
&nbsp;&nbsp;&nbsp;&nbsp;MM0 | MM1 | MM2 | MM3 | MM4 | MM5 | MM6 | MM7 | xmmRegister | 형식인 경우 YMM0 | YMM1 | YMM2 | YMM3 | YMM4 | YMM5 | YMM6 | YMM7 | YMM8 | YMM9 | YMM10 | YMM11 | YMM12 | YMM13 | YMM14 | YMM15

*simpleExpr*\
 ( *Cexpr* ) | *기본*

*simpleSegDir*\
&nbsp;&nbsp;&nbsp;&nbsp;*segDir* ;;

*sizeArg*\
&nbsp;&nbsp;&nbsp;&nbsp;*id* | *형식* | *e10*

*specialChars*\
 : | . | ⟦ | ⟧ | ( | ) | < | > | { | } \
&nbsp;&nbsp;&nbsp;&nbsp;| + | - | / | * | &AMP; | % | !\
&nbsp;&nbsp;&nbsp;&nbsp;| ' | \ | = | ; | , | "\
&nbsp;&nbsp;&nbsp;&nbsp;| *whiteSpaceCharacter*\
&nbsp;&nbsp;&nbsp;&nbsp;| *endOfLine*

*specialRegister*\
&nbsp;&nbsp;&nbsp;&nbsp;CR0 레지스터 | CR2 | CR3 | DR0 | DR1 | DR2 | DR3 | DR6 | DR7 | TR3 | TR4 | TR5 | TR6 | TR7

*Stackoption*\
&nbsp;&nbsp;&nbsp;&nbsp;**NEARSTACK** | **FARSTACK**

*Startupdir*\
&nbsp;&nbsp;&nbsp;&nbsp; **. 시작** ;;

*stext*\
&nbsp;&nbsp;&nbsp;&nbsp;*stringchar* | *stext* *stringchar*

*string*\
&nbsp;&nbsp;&nbsp;&nbsp;*quote* ⟦ *stext* ⟧ *따옴표*

*Stringchar*\
&nbsp;&nbsp;&nbsp;&nbsp;*견적* *따옴표* | 따옴표를 제외한 모든 문자입니다.

*structBody*\
&nbsp;&nbsp;&nbsp;&nbsp;*structItem* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;| *structBody* *structItem* ;;

*structDir*\
&nbsp;&nbsp;&nbsp;&nbsp;*structTag* *structHdr* ⟦ *fieldalign* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦, **고유** 하지 않은 ⟧;; \
&nbsp;&nbsp;&nbsp;&nbsp;*structBody*\
&nbsp;&nbsp;&nbsp;&nbsp;*structTag*\
&nbsp;&nbsp;&nbsp;&nbsp;**끝남** ;;

*structHdr*\
&nbsp;&nbsp;&nbsp;&nbsp;**STRUC** | **구조체** | **UNION**

*structInstance*\
 < ⟦ *Fieldinitlist* ⟧ > \
&nbsp;&nbsp;&nbsp;&nbsp;| {⟦;; ⟧ ⟦ *Fieldinitlist* ⟧ ⟦;; ⟧} \
&nbsp;&nbsp;&nbsp;&nbsp;| *constExpr* **DUP** ( *structInstList* ) \

*structInstList*\
&nbsp;&nbsp;&nbsp;&nbsp;*structInstance* | *structInstList* , ⟦;; ⟧ *structInstance*

*structItem*\
&nbsp;&nbsp;&nbsp;&nbsp;*Datadir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *일반 디렉터리*\
&nbsp;&nbsp;&nbsp;&nbsp;| *offsetDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *nestedStruct*

*structTag*\
&nbsp;&nbsp;&nbsp;&nbsp;*id*

*용어*\
&nbsp;&nbsp;&nbsp;&nbsp;*simpleExpr* |! *simpleExpr*

*text*\
&nbsp;&nbsp;&nbsp;&nbsp;*Textliteral* | *텍스트* 문자 |! *문자* *텍스트* | *문자* |! *문자*

*Textdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*id* *textMacroDir* ;;

*Textitem*\
&nbsp;&nbsp;&nbsp;&nbsp;*Textliteral* | *textMacroId* | % *constExpr*

*Textlen*\
*constExpr* &nbsp;&nbsp;&nbsp;&nbsp;

*Textlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*Textitem* | *textitem* , ⟦;; ⟧ *Textitem*

*Textliteral*\
&nbsp;&nbsp;&nbsp;&nbsp;< *텍스트* >;;

*textMacroDir*\
&nbsp;&nbsp;&nbsp;&nbsp;**Textlist** ⟦ *textlist* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| **TEXTEQU** ⟦ *textlist* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| **SIZESTR** *textitem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **SUBSTR** *textitem* , *Textitem* ⟦, *textitem* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| **INSTR** ⟦ *textstart* , ⟧ *textstart* , *textstart*

*textMacroId*\
&nbsp;&nbsp;&nbsp;&nbsp;*id*

*Textstart*\
*constExpr* &nbsp;&nbsp;&nbsp;&nbsp;

*titleDir*\
&nbsp;&nbsp;&nbsp;&nbsp;*titleType* *arbitraryText* ;;

*titleType*\
&nbsp;&nbsp;&nbsp;&nbsp;**제목** | **부제목** | **subttl**

*type*\
&nbsp;&nbsp;&nbsp;&nbsp;*structTag*\
&nbsp;&nbsp;&nbsp;&nbsp;| *unionTag*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Recordtag*\
&nbsp;&nbsp;&nbsp;&nbsp;| *거리*\
&nbsp;&nbsp;&nbsp;&nbsp;| *데이터 형식*\
&nbsp;&nbsp;&nbsp;&nbsp;| *typeId*

*Typedefdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*typeId* **TYPEDEF** 한정자

*typeId*\
&nbsp;&nbsp;&nbsp;&nbsp;*id*

*unionTag*\
&nbsp;&nbsp;&nbsp;&nbsp;*id*

*untilDir*\
&nbsp;&nbsp;&nbsp;&nbsp; **. UNTIL** *cexpr* ;; \
&nbsp;&nbsp;&nbsp;&nbsp; **. .UNTILCXZ** ⟦ *cxzexpr* ⟧;;

*\*
&nbsp;&nbsp;&nbsp;&nbsp;**USES** *reglist* 사용

*whileBlock*\
&nbsp;&nbsp;&nbsp;&nbsp; **.\**
&nbsp;&nbsp;&nbsp;&nbsp;*Cexpr* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*Blockstatements* ; \
&nbsp;&nbsp;&nbsp;&nbsp; **. ENDW**

*whiteSpaceCharacter*\
&nbsp;&nbsp;&nbsp;&nbsp;ASCII 8, 9, 11 – 13, 26, 32

*Xmmregister*\
&nbsp;&nbsp;&nbsp;&nbsp;XMM0 | XMM1 | XMM2 | XMM3 | XMM4 | ~ XMM5 | XMM6 | XMM7 | XMM8 | XMM9 | XMM10 | XMM11 | XMM12 | XMM13 | XMM14 | XMM15\
