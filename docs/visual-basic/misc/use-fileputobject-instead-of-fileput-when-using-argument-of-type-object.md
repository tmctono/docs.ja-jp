---
title: 型 'Object' の引数を使う場合は、'FilePut' ではなく 'FilePutObject' を使用してください。
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 3d793151905c61ee12eccdfdb5e9567a4924bb35
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022520"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a><span data-ttu-id="d9f35-102">型 'Object' の引数を使う場合は、'FilePut' ではなく 'FilePutObject' を使用してください。</span><span class="sxs-lookup"><span data-stu-id="d9f35-102">Use 'FilePutObject' instead of 'FilePut' when using argument of type 'Object'</span></span>
<span data-ttu-id="d9f35-103">`FilePut` メソッドには、型 `Object`の引数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d9f35-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="d9f35-104">あいまいさを避けるため、`FilePutObject` の代わりに `FilePut` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9f35-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d9f35-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="d9f35-105">To correct this error</span></span>  
  
- <span data-ttu-id="d9f35-106">`FilePut` を `FilePutObject`に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d9f35-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
- <span data-ttu-id="d9f35-107">`Object` 引数をより具体的な種類にキャストします。</span><span class="sxs-lookup"><span data-stu-id="d9f35-107">Cast the `Object` argument to a more specific type.</span></span>  
  
- <span data-ttu-id="d9f35-108">`My.Computer.FileSystem` オブジェクトで利用できる機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9f35-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9f35-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9f35-109">See also</span></span>

- [<span data-ttu-id="d9f35-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="d9f35-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [<span data-ttu-id="d9f35-111">My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="d9f35-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
