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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17e96f56c57d896397489e27bcc072d8e7df05ec
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796546"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="88c5b-102">IAssemblyName::SetProperty メソッド</span><span class="sxs-lookup"><span data-stu-id="88c5b-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="88c5b-103">指定したプロパティ識別子によって参照されるプロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="88c5b-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88c5b-104">構文</span><span class="sxs-lookup"><span data-stu-id="88c5b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88c5b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="88c5b-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="88c5b-106">から値が設定されるプロパティの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="88c5b-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="88c5b-107">からによって`PropertyId`参照されるプロパティを設定する値。</span><span class="sxs-lookup"><span data-stu-id="88c5b-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="88c5b-108">からの`pvProperty`サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="88c5b-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88c5b-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="88c5b-109">Requirements</span></span>  
 <span data-ttu-id="88c5b-110">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="88c5b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88c5b-111">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="88c5b-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="88c5b-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88c5b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88c5b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="88c5b-113">See also</span></span>

- [<span data-ttu-id="88c5b-114">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="88c5b-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
