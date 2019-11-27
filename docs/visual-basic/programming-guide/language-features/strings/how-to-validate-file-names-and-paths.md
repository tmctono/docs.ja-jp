---
title: '方法: ファイル名とパスを検証する'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: cc4d275d469860aa19c45ca0fe0401b709b42d82
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344363"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="f9405-102">方法 : Visual Basic でファイル名とパスを検証する</span><span class="sxs-lookup"><span data-stu-id="f9405-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="f9405-103">この例では、文字列がファイル名またはパスを表すかどうかを示す `Boolean` 値を返します。</span><span class="sxs-lookup"><span data-stu-id="f9405-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="f9405-104">検証では、ファイルシステムで許可されていない文字が名前に含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f9405-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9405-105">例</span><span class="sxs-lookup"><span data-stu-id="f9405-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 <span data-ttu-id="f9405-106">この例では、名前のコロンが誤って配置されているか、名前のないディレクトリがあるか、または名前の長さがシステムで定義されている最大長を超えていないかを確認しません。</span><span class="sxs-lookup"><span data-stu-id="f9405-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="f9405-107">また、指定した名前のファイルシステムリソースにアクセスするためのアクセス許可がアプリケーションにあるかどうかも確認しません。</span><span class="sxs-lookup"><span data-stu-id="f9405-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9405-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9405-108">See also</span></span>

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="f9405-109">Visual Basic における文字列の検証</span><span class="sxs-lookup"><span data-stu-id="f9405-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
