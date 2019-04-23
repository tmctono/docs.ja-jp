---
title: CloseAssembly メソッド
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94c1c083d010cd82fd9e9e2f02b23e81d88fedd5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116442"
---
# <a name="closeassembly-method"></a><span data-ttu-id="a6133-102">CloseAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="a6133-102">CloseAssembly Method</span></span>
<span data-ttu-id="a6133-103">アセンブリの操作を終了します。</span><span class="sxs-lookup"><span data-stu-id="a6133-103">Finalizes assembly operations.</span></span> <span data-ttu-id="a6133-104">新しいアセンブリまたはバインドされていないモジュールを開始する前に、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a6133-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6133-105">構文</span><span class="sxs-lookup"><span data-stu-id="a6133-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6133-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a6133-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a6133-107">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="a6133-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6133-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="a6133-108">Return Value</span></span>  
 <span data-ttu-id="a6133-109">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="a6133-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6133-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="a6133-110">Requirements</span></span>  
 <span data-ttu-id="a6133-111">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="a6133-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6133-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6133-112">See also</span></span>

- [<span data-ttu-id="a6133-113">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6133-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a6133-114">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6133-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a6133-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="a6133-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
