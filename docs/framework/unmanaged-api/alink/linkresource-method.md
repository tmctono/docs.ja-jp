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
ms.openlocfilehash: 6e851c1bd56c0e9ece02fb06c0dcd9975a5b02ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079437"
---
# <a name="linkresource-method"></a><span data-ttu-id="c3c60-102">LinkResource メソッド</span><span class="sxs-lookup"><span data-stu-id="c3c60-102">LinkResource Method</span></span>
<span data-ttu-id="c3c60-103">リソースにリンクします。</span><span class="sxs-lookup"><span data-stu-id="c3c60-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3c60-104">構文</span><span class="sxs-lookup"><span data-stu-id="c3c60-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3c60-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3c60-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c3c60-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="c3c60-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="c3c60-107">ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="c3c60-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="c3c60-108">省略可能な新しいファイル名。</span><span class="sxs-lookup"><span data-stu-id="c3c60-108">Optional new file name.</span></span> <span data-ttu-id="c3c60-109">NULL 以外の場合`pszFileName`pszNewLocation にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="c3c60-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="c3c60-110">リソースの名前。</span><span class="sxs-lookup"><span data-stu-id="c3c60-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c3c60-111">ユーザー補助フラグなど`mrPublic`と`mrPrivate`します。</span><span class="sxs-lookup"><span data-stu-id="c3c60-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="c3c60-112">このパラメーターに渡される[DefineManifestResource メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="c3c60-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3c60-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="c3c60-113">Return Value</span></span>  
 <span data-ttu-id="c3c60-114">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="c3c60-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3c60-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="c3c60-115">Requirements</span></span>  
 <span data-ttu-id="c3c60-116">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="c3c60-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3c60-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3c60-117">See also</span></span>

- [<span data-ttu-id="c3c60-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3c60-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="c3c60-119">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3c60-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="c3c60-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="c3c60-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
