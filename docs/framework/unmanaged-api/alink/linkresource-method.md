---
title: LinkResource メソッド
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 763b7a776007c2ce8dac42c6a5f7f00f6eb58a10
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776944"
---
# <a name="linkresource-method"></a><span data-ttu-id="ae9de-102">LinkResource メソッド</span><span class="sxs-lookup"><span data-stu-id="ae9de-102">LinkResource Method</span></span>
<span data-ttu-id="ae9de-103">リソース内のリンク。</span><span class="sxs-lookup"><span data-stu-id="ae9de-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae9de-104">構文</span><span class="sxs-lookup"><span data-stu-id="ae9de-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae9de-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ae9de-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ae9de-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="ae9de-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="ae9de-107">ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="ae9de-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="ae9de-108">省略可能な新しいファイル名。</span><span class="sxs-lookup"><span data-stu-id="ae9de-108">Optional new file name.</span></span> <span data-ttu-id="ae9de-109">NULL 以外の場合は`pszFileName` 、psznewlocation にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="ae9de-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="ae9de-110">リソースの名前。</span><span class="sxs-lookup"><span data-stu-id="ae9de-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ae9de-111">`mrPublic` や`mrPrivate`などのアクセシビリティフラグ。</span><span class="sxs-lookup"><span data-stu-id="ae9de-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="ae9de-112">このパラメーターは、 [DefineManifestResource メソッド](../metadata/imetadataassemblyemit-definemanifestresource-method.md)に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="ae9de-112">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae9de-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="ae9de-113">Return Value</span></span>  
 <span data-ttu-id="ae9de-114">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="ae9de-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae9de-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="ae9de-115">Requirements</span></span>  
 <span data-ttu-id="ae9de-116">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="ae9de-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9de-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae9de-117">See also</span></span>

- [<span data-ttu-id="ae9de-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae9de-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ae9de-119">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae9de-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ae9de-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="ae9de-120">ALink API</span></span>](index.md)
