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
ms.openlocfilehash: 335d80255f7a3f5a22e8a69aa91c9e5b0843ea1e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741592"
---
# <a name="linkresource-method"></a><span data-ttu-id="fbd8e-102">LinkResource メソッド</span><span class="sxs-lookup"><span data-stu-id="fbd8e-102">LinkResource Method</span></span>
<span data-ttu-id="fbd8e-103">リソースにリンクします。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbd8e-104">構文</span><span class="sxs-lookup"><span data-stu-id="fbd8e-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbd8e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fbd8e-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fbd8e-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="fbd8e-107">ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="fbd8e-108">省略可能な新しいファイル名。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-108">Optional new file name.</span></span> <span data-ttu-id="fbd8e-109">NULL 以外の場合`pszFileName`pszNewLocation にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="fbd8e-110">リソースの名前。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fbd8e-111">ユーザー補助フラグなど`mrPublic`と`mrPrivate`します。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="fbd8e-112">このパラメーターに渡される[DefineManifestResource メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbd8e-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="fbd8e-113">Return Value</span></span>  
 <span data-ttu-id="fbd8e-114">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbd8e-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="fbd8e-115">Requirements</span></span>  
 <span data-ttu-id="fbd8e-116">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbd8e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbd8e-117">See also</span></span>

- [<span data-ttu-id="fbd8e-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbd8e-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="fbd8e-119">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbd8e-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="fbd8e-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="fbd8e-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
