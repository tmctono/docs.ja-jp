---
title: TextFieldParser は空白を含むコメントトークンをサポートしていません
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: 825f999f8eab3563dd77039ef19ae5e329bb4240
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078503"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a><span data-ttu-id="afb55-102">TextFieldParser は空白を含むコメントトークンをサポートしていません</span><span class="sxs-lookup"><span data-stu-id="afb55-102">TextFieldParser does not support comment tokens that contain white space</span></span>

<span data-ttu-id="afb55-103">空白を含むコメント トークンが指定されています。</span><span class="sxs-lookup"><span data-stu-id="afb55-103">A comment token that contains white space has been supplied.</span></span> <span data-ttu-id="afb55-104">トークンの先頭に空白がある場合を除き、 `TextFieldParser` は空白を含むコメント トークンをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="afb55-104">The `TextFieldParser` does not support comment tokens that contain white space unless the white space occurs at the beginning of the token.</span></span> <span data-ttu-id="afb55-105">トークンの先頭にある空白は無視されます。</span><span class="sxs-lookup"><span data-stu-id="afb55-105">White space occurring at the beginning of a token is ignored.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="afb55-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="afb55-106">To correct this error</span></span>  
  
- <span data-ttu-id="afb55-107">適切なコメント トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="afb55-107">Supply a correct comment token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb55-108">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="afb55-108">See also</span></span>

- [<span data-ttu-id="afb55-109">TextFieldParser.CommentTokens プロパティ</span><span class="sxs-lookup"><span data-stu-id="afb55-109">TextFieldParser.CommentTokens Property</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)
- [<span data-ttu-id="afb55-110">TextFieldParser オブジェクトによるテキスト ファイルの解析</span><span class="sxs-lookup"><span data-stu-id="afb55-110">Parsing Text Files with the TextFieldParser Object</span></span>](../developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="afb55-111">TextFieldParser Object</span><span class="sxs-lookup"><span data-stu-id="afb55-111">TextFieldParser Object</span></span>](../language-reference/objects/textfieldparser-object.md)
