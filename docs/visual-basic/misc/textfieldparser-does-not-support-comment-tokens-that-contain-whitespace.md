---
title: TextFieldParser は空白を含むコメント トークンをサポートしていません
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: af0f09bb7a8afc3b6e63cfab1a7176ba26cf20a6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64660892"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a><span data-ttu-id="eab27-102">TextFieldParser は空白を含むコメント トークンをサポートしていません</span><span class="sxs-lookup"><span data-stu-id="eab27-102">TextFieldParser does not support comment tokens that contain white space</span></span>
<span data-ttu-id="eab27-103">空白を含むコメント トークンが指定されています。</span><span class="sxs-lookup"><span data-stu-id="eab27-103">A comment token that contains white space has been supplied.</span></span> <span data-ttu-id="eab27-104">トークンの先頭に空白がある場合を除き、 `TextFieldParser` は空白を含むコメント トークンをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="eab27-104">The `TextFieldParser` does not support comment tokens that contain white space unless the white space occurs at the beginning of the token.</span></span> <span data-ttu-id="eab27-105">トークンの先頭にある空白は無視されます。</span><span class="sxs-lookup"><span data-stu-id="eab27-105">White space occurring at the beginning of a token is ignored.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eab27-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="eab27-106">To correct this error</span></span>  
  
- <span data-ttu-id="eab27-107">適切なコメント トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="eab27-107">Supply a correct comment token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eab27-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="eab27-108">See also</span></span>

- [<span data-ttu-id="eab27-109">TextFieldParser.CommentTokens プロパティ</span><span class="sxs-lookup"><span data-stu-id="eab27-109">TextFieldParser.CommentTokens Property</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)
- [<span data-ttu-id="eab27-110">TextFieldParser オブジェクトによるテキスト ファイルの解析</span><span class="sxs-lookup"><span data-stu-id="eab27-110">Parsing Text Files with the TextFieldParser Object</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="eab27-111">TextFieldParser オブジェクト</span><span class="sxs-lookup"><span data-stu-id="eab27-111">TextFieldParser Object</span></span>](../../visual-basic/language-reference/objects/textfieldparser-object.md)
