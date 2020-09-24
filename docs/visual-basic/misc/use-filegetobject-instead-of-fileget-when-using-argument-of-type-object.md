---
title: 型 'Object' の引数を使用する場合は、'FileGet' ではなく 'FileGetObject' を使用してください。
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 318a0772a99aa86d9a4633e6021f77616a43fc7e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059406"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a><span data-ttu-id="c277e-102">型 'Object' の引数を使用する場合は、'FileGet' ではなく 'FileGetObject' を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c277e-102">Use 'FileGetObject' instead of 'FileGet' when using argument of type 'Object'</span></span>

<span data-ttu-id="c277e-103">`FileGet` メソッドには、型 `Object`の引数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c277e-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="c277e-104">あいまいさを避けるため、`FileGetObject` の代わりに `FileGet` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c277e-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="c277e-105">`My.Computer.Filesystem` によって提供される機能は、`FileGet` または `FileGetObject` よりも使いやすく、パフォーマンスが優れています。</span><span class="sxs-lookup"><span data-stu-id="c277e-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c277e-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="c277e-106">To correct this error</span></span>  
  
1. <span data-ttu-id="c277e-107">`FileGet` を `FileGetObject` で置き換え</span><span class="sxs-lookup"><span data-stu-id="c277e-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2. <span data-ttu-id="c277e-108">`Object` 引数をより具体的な種類にキャストします。</span><span class="sxs-lookup"><span data-stu-id="c277e-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c277e-109">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="c277e-109">See also</span></span>

- [<span data-ttu-id="c277e-110">マイファイル (コンピューター)</span><span class="sxs-lookup"><span data-stu-id="c277e-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
