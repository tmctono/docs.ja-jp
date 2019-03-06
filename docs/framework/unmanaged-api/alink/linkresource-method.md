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
ms.openlocfilehash: 61f82a34c287c62e1180c9c6bbe090914763afa3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479087"
---
# <a name="linkresource-method"></a><span data-ttu-id="119dd-102">LinkResource メソッド</span><span class="sxs-lookup"><span data-stu-id="119dd-102">LinkResource Method</span></span>
<span data-ttu-id="119dd-103">リソースにリンクします。</span><span class="sxs-lookup"><span data-stu-id="119dd-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="119dd-104">構文</span><span class="sxs-lookup"><span data-stu-id="119dd-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="119dd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="119dd-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="119dd-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="119dd-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="119dd-107">ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="119dd-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="119dd-108">省略可能な新しいファイル名。</span><span class="sxs-lookup"><span data-stu-id="119dd-108">Optional new file name.</span></span> <span data-ttu-id="119dd-109">NULL 以外の場合`pszFileName`pszNewLocation にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="119dd-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="119dd-110">リソースの名前。</span><span class="sxs-lookup"><span data-stu-id="119dd-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="119dd-111">ユーザー補助フラグなど`mrPublic`と`mrPrivate`します。</span><span class="sxs-lookup"><span data-stu-id="119dd-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="119dd-112">このパラメーターに渡される[DefineManifestResource メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="119dd-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="119dd-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="119dd-113">Return Value</span></span>  
 <span data-ttu-id="119dd-114">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="119dd-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="119dd-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="119dd-115">Requirements</span></span>  
 <span data-ttu-id="119dd-116">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="119dd-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="119dd-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="119dd-117">See also</span></span>
- [<span data-ttu-id="119dd-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="119dd-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="119dd-119">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="119dd-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="119dd-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="119dd-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
