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
ms.openlocfilehash: 2dcb363a2a84b3c2e0438e45663b96d9a0f83f61
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445554"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="1b420-102">SetNonAssemblyFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="1b420-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="1b420-103">アセンブリ固有ではないフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="1b420-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b420-104">構文</span><span class="sxs-lookup"><span data-stu-id="1b420-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b420-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1b420-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="1b420-106">ALink フラグ。</span><span class="sxs-lookup"><span data-stu-id="1b420-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b420-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="1b420-107">Return Value</span></span>  
 <span data-ttu-id="1b420-108">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="1b420-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b420-109">要件</span><span class="sxs-lookup"><span data-stu-id="1b420-109">Requirements</span></span>  
 <span data-ttu-id="1b420-110">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="1b420-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b420-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b420-111">See also</span></span>

- [<span data-ttu-id="1b420-112">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b420-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="1b420-113">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b420-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="1b420-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="1b420-114">ALink API</span></span>](index.md)
