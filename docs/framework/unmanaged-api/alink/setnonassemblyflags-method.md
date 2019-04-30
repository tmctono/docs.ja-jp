---
title: SetNonAssemblyFlags メソッド
ms.date: 03/30/2017
api_name:
- IALink.SetNonAssemblyFlags
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetNonAssemblyFlags
helpviewer_keywords:
- SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c7716db814e86258c4cb81047b39142f33798782
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949025"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="08ae6-102">SetNonAssemblyFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="08ae6-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="08ae6-103">アセンブリに固有でないフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="08ae6-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08ae6-104">構文</span><span class="sxs-lookup"><span data-stu-id="08ae6-104">Syntax</span></span>  
  
```  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="08ae6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="08ae6-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="08ae6-106">ALink フラグ。</span><span class="sxs-lookup"><span data-stu-id="08ae6-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08ae6-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="08ae6-107">Return Value</span></span>  
 <span data-ttu-id="08ae6-108">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="08ae6-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08ae6-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="08ae6-109">Requirements</span></span>  
 <span data-ttu-id="08ae6-110">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="08ae6-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08ae6-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="08ae6-111">See also</span></span>

- [<span data-ttu-id="08ae6-112">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="08ae6-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="08ae6-113">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="08ae6-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="08ae6-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="08ae6-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
