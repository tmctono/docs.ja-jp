---
title: '方法: 符号なしの型を受け取る Windows 関数を呼び出す (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
ms.openlocfilehash: 97075fb6149ed8c0ce06318d0e5bb6f01b841f30
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053323"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a><span data-ttu-id="ccd87-102">方法: 符号なしの型を受け取る Windows 関数を呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ccd87-102">How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)</span></span>

<span data-ttu-id="ccd87-103">符号なし整数型のメンバーを持つクラス、モジュール、または構造体を使用している場合、これらのメンバーには Visual Basic でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ccd87-103">If you are consuming a class, module, or structure that has members of unsigned integer types, you can access these members with Visual Basic.</span></span>

## <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a><span data-ttu-id="ccd87-104">符号なしの型を受け取る Windows 関数を呼び出すには</span><span class="sxs-lookup"><span data-stu-id="ccd87-104">To call a Windows function that takes an unsigned type</span></span>

1. <span data-ttu-id="ccd87-105">[Declare ステートメント](../../../visual-basic/language-reference/statements/declare-statement.md)を使用して、どのライブラリに関数が格納されているか、そのライブラリ内でその名前がどのようなものであるか、呼び出し元のシーケンスについて、および文字列を呼び出すときに文字列を変換する方法を Visual Basic 通知します。</span><span class="sxs-lookup"><span data-stu-id="ccd87-105">Use a [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) to tell Visual Basic which library holds the function, what its name is in that library, what its calling sequence is, and how to convert strings when calling it.</span></span>

2. <span data-ttu-id="ccd87-106">`ULong` `UInteger` `Byte` `UShort`ステートメントでは、符号なしの型を持つ各パラメーターに適切な、、、、またはを使用します。 `Declare`</span><span class="sxs-lookup"><span data-stu-id="ccd87-106">In the `Declare` statement, use `UInteger`, `ULong`, `UShort`, or `Byte` as appropriate for each parameter with an unsigned type.</span></span>

3. <span data-ttu-id="ccd87-107">使用している定数の名前と値を調べるには、呼び出し元の Windows 関数のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccd87-107">Consult the documentation for the Windows function you are calling to find the names and values of the constants it uses.</span></span> <span data-ttu-id="ccd87-108">これらの多くは、WinUser .h ファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="ccd87-108">Many of these are defined in the WinUser.h file.</span></span>

4. <span data-ttu-id="ccd87-109">コードで必要な定数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="ccd87-109">Declare the necessary constants in your code.</span></span> <span data-ttu-id="ccd87-110">多くの Windows 定数は、32ビットの符号なしの値である`As UInteger`ため、これらを宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccd87-110">Many Windows constants are 32-bit unsigned values, and you should declare these `As UInteger`.</span></span>

5. <span data-ttu-id="ccd87-111">通常の方法で関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ccd87-111">Call the function in the normal way.</span></span> <span data-ttu-id="ccd87-112">次の例では、Windows `MessageBox`関数を呼び出します。この関数は、符号なし整数引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ccd87-112">The following example calls the Windows function `MessageBox`, which takes an unsigned integer argument.</span></span>

    ```vb
    Public Class windowsMessage
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (
            ByVal hWnd As Integer,
            ByVal lpText As String,
            ByVal lpCaption As String,
            ByVal uType As UInteger) As Integer
        Private Const MB_OK As UInteger = 0
        Private Const MB_ICONEXCLAMATION As UInteger = &H30
        Private Const IDOK As UInteger = 1
        Private Const IDCLOSE As UInteger = 8
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION
        Public Function messageThroughWindows() As String
            Dim r As Integer = mb(0, "Click OK if you see this!",
                "Windows API call", c)
            Dim s As String = "Windows API MessageBox returned " &
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"
            Return s
        End Function
    End Class
    ```

     <span data-ttu-id="ccd87-113">関数`messageThroughWindows`をテストするには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ccd87-113">You can test the function `messageThroughWindows` with the following code.</span></span>

    ```vb
    Public Sub consumeWindowsMessage()
        Dim w As New windowsMessage
        w.messageThroughWindows()
    End Sub
    ```

    > [!CAUTION]
    > <span data-ttu-id="ccd87-114">`UInteger` 、`ULong`、 、および`SByte`の各データ型は、言語への非[依存性と言語に依存](../../../standard/language-independence-and-language-independent-components.md)しないコンポーネント (cls) の一部ではないため、cls 準拠のコードでは、それらを使用するコンポーネントを使用できません。 `UShort`</span><span class="sxs-lookup"><span data-stu-id="ccd87-114">The `UInteger`, `ULong`, `UShort`, and `SByte` data types are not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot consume a component that uses them.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ccd87-115">Windows アプリケーションプログラミングインターフェイス (API) などのアンマネージコードを呼び出すと、潜在的なセキュリティリスクに対してコードが公開されます。</span><span class="sxs-lookup"><span data-stu-id="ccd87-115">Making a call to unmanaged code, such as the Windows application programming interface (API), exposes your code to potential security risks.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ccd87-116">Windows API を呼び出すには、アンマネージコードのアクセス許可が必要です。これは、部分信頼状況での実行に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ccd87-116">Calling the Windows API requires unmanaged code permission, which might affect its execution in partial-trust situations.</span></span> <span data-ttu-id="ccd87-117">詳細については<xref:System.Security.Permissions.SecurityPermission> 、「」および「[コードアクセス許可](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccd87-117">For more information, see <xref:System.Security.Permissions.SecurityPermission> and [Code Access Permissions](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100)).</span></span>

## <a name="see-also"></a><span data-ttu-id="ccd87-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccd87-118">See also</span></span>

- [<span data-ttu-id="ccd87-119">データの種類</span><span class="sxs-lookup"><span data-stu-id="ccd87-119">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="ccd87-120">Integer データ型</span><span class="sxs-lookup"><span data-stu-id="ccd87-120">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="ccd87-121">UInteger データ型</span><span class="sxs-lookup"><span data-stu-id="ccd87-121">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)
- [<span data-ttu-id="ccd87-122">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="ccd87-122">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="ccd87-123">チュートリアル: Windows API の呼び出し</span><span class="sxs-lookup"><span data-stu-id="ccd87-123">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
