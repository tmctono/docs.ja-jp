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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135181"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="30e2e-102">GetResolutionScope メソッド</span><span class="sxs-lookup"><span data-stu-id="30e2e-102">GetResolutionScope Method</span></span>
<span data-ttu-id="30e2e-103">指定された型のスコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="30e2e-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e2e-104">構文</span><span class="sxs-lookup"><span data-stu-id="30e2e-104">Syntax</span></span>  
  
```  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="30e2e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="30e2e-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="30e2e-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="30e2e-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="30e2e-107">参照が必要なファイル。</span><span class="sxs-lookup"><span data-stu-id="30e2e-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="30e2e-108">その型が定義されているファイルのトークン[ImportFile メソッド](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="30e2e-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="30e2e-109">アセンブリまたはモジュールの参照を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="30e2e-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30e2e-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="30e2e-110">Return Value</span></span>  
 <span data-ttu-id="30e2e-111">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="30e2e-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30e2e-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="30e2e-112">Requirements</span></span>  
 <span data-ttu-id="30e2e-113">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="30e2e-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30e2e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="30e2e-114">See also</span></span>

- [<span data-ttu-id="30e2e-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="30e2e-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="30e2e-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="30e2e-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="30e2e-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="30e2e-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
