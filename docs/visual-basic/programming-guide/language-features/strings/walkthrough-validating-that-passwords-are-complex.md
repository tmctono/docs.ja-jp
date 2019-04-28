---
title: パスワードの複雑さ (Visual Basic) を検証しています
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 829d6485acdca22fbf10160c734e5c7f931dd855
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938256"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="4104b-102">チュートリアル: パスワードの複雑な検証 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4104b-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="4104b-103">このメソッドは、いくつかの強力なパスワードの特性を確認し、失敗、パスワードをチェックに関する情報を含む文字列パラメーターを更新します。</span><span class="sxs-lookup"><span data-stu-id="4104b-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="4104b-104">パスワードは、ユーザーを承認するために、セキュリティで保護されたシステムで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4104b-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="4104b-105">ただし、パスワードは、承認されていないユーザーを推測するが困難である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4104b-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="4104b-106">攻撃者が使用できる、*辞書攻撃*プログラムでは、ディクショナリ (または別の言語で複数の辞書) 内の単語のすべてを反復処理し、ユーザーのパスワードとして機能、単語のいずれかであるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="4104b-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="4104b-107">「ヤンキース」または「マスタング」などの脆弱なパスワードを簡単に推測できることができます。</span><span class="sxs-lookup"><span data-stu-id="4104b-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="4104b-108">強力なパスワードは、たとえば"でしょうか。'L1N3vaFiNdMeyeP@sSWerd!"が大幅に低下を推測できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4104b-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="4104b-109">パスワードで保護されたシステムでは、ユーザーが強力なパスワードを選択することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4104b-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="4104b-110">強力なパスワードは、(大文字、小文字、数字、および特殊文字の組み合わせを含む) 複合語ではないです。</span><span class="sxs-lookup"><span data-stu-id="4104b-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="4104b-111">この例では、複雑さを検証する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4104b-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4104b-112">例</span><span class="sxs-lookup"><span data-stu-id="4104b-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="4104b-113">コード</span><span class="sxs-lookup"><span data-stu-id="4104b-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4104b-114">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="4104b-114">Compiling the Code</span></span>  
 <span data-ttu-id="4104b-115">パスワードを格納する文字列を渡すことによって、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4104b-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="4104b-116">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4104b-116">This example requires:</span></span>  
  
- <span data-ttu-id="4104b-117"><xref:System.Text.RegularExpressions> 名前空間のメンバーへのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="4104b-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="4104b-118">コード内でメンバー名を完全修飾していない場合は、`Imports` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="4104b-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="4104b-119">詳細については、「[Imports ステートメント (.NET 名前空間および型)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4104b-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="4104b-120">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="4104b-120">Security</span></span>  
 <span data-ttu-id="4104b-121">パスワードをネットワーク経由で移動する場合は、データを転送するためのセキュリティで保護されたメソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4104b-121">If you're moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="4104b-122">詳細については、次を参照してください。 [ASP.NET Web アプリケーションのセキュリティ](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="4104b-122">For more information, see [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span></span>
  
 <span data-ttu-id="4104b-123">精度を向上させることができます、`ValidatePassword`の他の複雑性チェックを追加することで機能します。</span><span class="sxs-lookup"><span data-stu-id="4104b-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
- <span data-ttu-id="4104b-124">パスワードとユーザーの名前、ユーザー識別子、およびアプリケーション定義の辞書からその部分文字列を比較します。</span><span class="sxs-lookup"><span data-stu-id="4104b-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="4104b-125">さらに、比較を実行するときに、視覚的に類似する文字と同等として扱われます。</span><span class="sxs-lookup"><span data-stu-id="4104b-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="4104b-126">たとえば、「1」と「3」の数字と同等として文字"l"と"e"を扱います。</span><span class="sxs-lookup"><span data-stu-id="4104b-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
- <span data-ttu-id="4104b-127">1 つだけに大文字がある場合、パスワードの最初の文字ではないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4104b-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
- <span data-ttu-id="4104b-128">パスワードの最後の 2 つの文字がアルファベットの文字であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4104b-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
- <span data-ttu-id="4104b-129">キーボードの一番上の行からのすべてのシンボルが入力されるパスワードは許可されません。</span><span class="sxs-lookup"><span data-stu-id="4104b-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4104b-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="4104b-130">See also</span></span>

- <xref:System.Text.RegularExpressions.Regex>
- <span data-ttu-id="4104b-131">[ASP.NET Web アプリケーションのセキュリティ](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4104b-131">[ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span></span>
