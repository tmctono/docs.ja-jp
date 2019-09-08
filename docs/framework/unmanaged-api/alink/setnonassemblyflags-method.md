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
ms.openlocfilehash: e8a22e958740b69ba0e09bf062bf4d86075c3ff1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777010"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="0f656-102">SetNonAssemblyFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="0f656-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="0f656-103">アセンブリ固有ではないフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="0f656-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f656-104">構文</span><span class="sxs-lookup"><span data-stu-id="0f656-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f656-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f656-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="0f656-106">ALink フラグ。</span><span class="sxs-lookup"><span data-stu-id="0f656-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f656-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="0f656-107">Return Value</span></span>  
 <span data-ttu-id="0f656-108">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="0f656-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f656-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="0f656-109">Requirements</span></span>  
 <span data-ttu-id="0f656-110">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="0f656-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f656-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f656-111">See also</span></span>

- [<span data-ttu-id="0f656-112">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0f656-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="0f656-113">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0f656-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="0f656-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="0f656-114">ALink API</span></span>](index.md)
