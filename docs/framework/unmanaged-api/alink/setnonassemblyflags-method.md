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
ms.openlocfilehash: 27ad89f1910bc7bb08a23c9fdb0d50828fb8b5e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741442"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="b4ccb-102">SetNonAssemblyFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="b4ccb-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="b4ccb-103">アセンブリに固有でないフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="b4ccb-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4ccb-104">構文</span><span class="sxs-lookup"><span data-stu-id="b4ccb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4ccb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b4ccb-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="b4ccb-106">ALink フラグ。</span><span class="sxs-lookup"><span data-stu-id="b4ccb-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4ccb-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="b4ccb-107">Return Value</span></span>  
 <span data-ttu-id="b4ccb-108">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="b4ccb-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4ccb-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="b4ccb-109">Requirements</span></span>  
 <span data-ttu-id="b4ccb-110">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="b4ccb-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ccb-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4ccb-111">See also</span></span>

- [<span data-ttu-id="b4ccb-112">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4ccb-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b4ccb-113">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4ccb-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b4ccb-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="b4ccb-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
