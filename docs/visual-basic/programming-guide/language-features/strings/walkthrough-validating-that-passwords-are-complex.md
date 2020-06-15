---
title: パスワードの複雑さの検証
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 49e6f79c13c94a3f2f6891b259c4bb2bec54ae6f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344521"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="9f69f-102">チュートリアル: パスワードの複雑さの検証 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f69f-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="9f69f-103">このメソッドでは、強力なパスワードの特性をチェックし、不合格になったチェックに関する情報で文字列パラメーターを更新します。</span><span class="sxs-lookup"><span data-stu-id="9f69f-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="9f69f-104">セキュリティで保護されたシステムでは、パスワードを使用してユーザーを承認できます。</span><span class="sxs-lookup"><span data-stu-id="9f69f-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="9f69f-105">ただし、パスワードは、承認されていないユーザーが推測するのは難しいものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f69f-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="9f69f-106">攻撃者は、辞書 (またはさまざまな言語の複数の辞書) のすべての単語を反復処理する "*辞書攻撃*" プログラムを使用し、単語のいずれかがユーザーのパスワードとして機能するかどうかをテストする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9f69f-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="9f69f-107">"Yankees" や "Mustang" のような脆弱なパスワードはすぐに推測できます。</span><span class="sxs-lookup"><span data-stu-id="9f69f-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="9f69f-108">"?You'L1N3vaFiNdMeyeP@sSWerd!" のような強力なパスワードは、推測される可能性がはるかに低くなります。</span><span class="sxs-lookup"><span data-stu-id="9f69f-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="9f69f-109">パスワードで保護されたシステムでは、ユーザーが強力なパスワードを選択できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f69f-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="9f69f-110">強力なパスワードは複雑であり (大文字、小文字、数字、特殊文字が混在)、単語ではありません。</span><span class="sxs-lookup"><span data-stu-id="9f69f-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="9f69f-111">次の例は、複雑さを検証する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9f69f-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f69f-112">例</span><span class="sxs-lookup"><span data-stu-id="9f69f-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="9f69f-113">コード</span><span class="sxs-lookup"><span data-stu-id="9f69f-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="9f69f-114">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="9f69f-114">Compile the code</span></span>  
 <span data-ttu-id="9f69f-115">対象のパスワードを含む文字列を渡して、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9f69f-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="9f69f-116">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9f69f-116">This example requires:</span></span>  
  
- <span data-ttu-id="9f69f-117"><xref:System.Text.RegularExpressions> 名前空間のメンバーへのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="9f69f-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="9f69f-118">コード内でメンバー名を完全修飾していない場合は、`Imports` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="9f69f-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="9f69f-119">詳細については、「[Imports ステートメント (.NET 名前空間および型)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f69f-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="9f69f-120">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="9f69f-120">Security</span></span>  
 <span data-ttu-id="9f69f-121">ネットワーク経由でパスワードを移動する場合は、セキュリティで保護された方法でデータを転送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f69f-121">If you're moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="9f69f-122">詳細については、「[ASP.NET Web Application Security (ASP.NET Web アプリケーションのセキュリティ)](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9f69f-122">For more information, see [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span></span>
  
 <span data-ttu-id="9f69f-123">複雑さのチェックをさらに追加することで、`ValidatePassword` 関数の精度を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="9f69f-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
- <span data-ttu-id="9f69f-124">パスワードとその部分文字列を、ユーザーの名前、ユーザー識別子、アプリケーション定義の辞書と比較します。</span><span class="sxs-lookup"><span data-stu-id="9f69f-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="9f69f-125">さらに、比較を行うときに、見た目が似ている文字は同等に扱います。</span><span class="sxs-lookup"><span data-stu-id="9f69f-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="9f69f-126">たとえば、文字 "l"、"e" は数字 "1"、"3" と同等に扱います。</span><span class="sxs-lookup"><span data-stu-id="9f69f-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
- <span data-ttu-id="9f69f-127">大文字が 1 つしかない場合は、パスワードの最初の文字ではないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f69f-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
- <span data-ttu-id="9f69f-128">パスワードの最後の 2 文字が文字であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f69f-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
- <span data-ttu-id="9f69f-129">すべての記号がキーボードの上部の行から入力されているパスワードは許可しないでください。</span><span class="sxs-lookup"><span data-stu-id="9f69f-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f69f-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f69f-130">See also</span></span>

- <xref:System.Text.RegularExpressions.Regex>
- <span data-ttu-id="9f69f-131">[ASP.NET Web アプリケーションのセキュリティ](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9f69f-131">[ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span></span>
