---
title: GetResolutionScope メソッド
ms.date: 03/30/2017
api_name:
- IALink.GetResolutionScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetResolutionScope
helpviewer_keywords:
- GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c6d298c84b801b87832c56026b05f647cb5a9dd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135181"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="5514f-102">GetResolutionScope メソッド</span><span class="sxs-lookup"><span data-stu-id="5514f-102">GetResolutionScope Method</span></span>
<span data-ttu-id="5514f-103">指定された型のスコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="5514f-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5514f-104">構文</span><span class="sxs-lookup"><span data-stu-id="5514f-104">Syntax</span></span>  
  
```  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5514f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5514f-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="5514f-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="5514f-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="5514f-107">参照が必要なファイル。</span><span class="sxs-lookup"><span data-stu-id="5514f-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="5514f-108">その型が定義されているファイルのトークン[ImportFile メソッド](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="5514f-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="5514f-109">アセンブリまたはモジュールの参照を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5514f-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5514f-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="5514f-110">Return Value</span></span>  
 <span data-ttu-id="5514f-111">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="5514f-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5514f-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="5514f-112">Requirements</span></span>  
 <span data-ttu-id="5514f-113">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="5514f-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5514f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5514f-114">See also</span></span>

- [<span data-ttu-id="5514f-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5514f-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="5514f-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5514f-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="5514f-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="5514f-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
