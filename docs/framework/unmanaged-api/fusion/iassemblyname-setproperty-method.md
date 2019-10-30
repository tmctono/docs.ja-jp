---
title: IAssemblyName::SetProperty メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
ms.openlocfilehash: ffa1fa2f5e141728a56f1b598a1aae9602b2ac86
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108215"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="04852-102">IAssemblyName::SetProperty メソッド</span><span class="sxs-lookup"><span data-stu-id="04852-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="04852-103">指定したプロパティ識別子によって参照されるプロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="04852-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04852-104">構文</span><span class="sxs-lookup"><span data-stu-id="04852-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04852-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04852-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="04852-106">から値が設定されるプロパティの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="04852-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="04852-107">から`PropertyId`によって参照されるプロパティを設定する値。</span><span class="sxs-lookup"><span data-stu-id="04852-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="04852-108">から`pvProperty`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="04852-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04852-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="04852-109">Requirements</span></span>  
 <span data-ttu-id="04852-110">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04852-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04852-111">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="04852-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="04852-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04852-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04852-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="04852-113">See also</span></span>

- [<span data-ttu-id="04852-114">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="04852-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
