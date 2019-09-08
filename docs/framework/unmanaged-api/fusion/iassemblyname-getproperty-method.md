---
title: IAssemblyName::GetProperty メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 351d540d226f46f180b46323e83eb1bcc71da4f0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796592"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="536d6-102">IAssemblyName::GetProperty メソッド</span><span class="sxs-lookup"><span data-stu-id="536d6-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="536d6-103">指定したプロパティ識別子によって参照されるプロパティへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="536d6-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="536d6-104">構文</span><span class="sxs-lookup"><span data-stu-id="536d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="536d6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="536d6-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="536d6-106">から要求されたプロパティの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="536d6-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="536d6-107">入出力返されたプロパティデータ。</span><span class="sxs-lookup"><span data-stu-id="536d6-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="536d6-108">[入力、出力]の`pvProperty`サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="536d6-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="536d6-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="536d6-109">Requirements</span></span>  
 <span data-ttu-id="536d6-110">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="536d6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="536d6-111">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="536d6-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="536d6-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="536d6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="536d6-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="536d6-113">See also</span></span>

- [<span data-ttu-id="536d6-114">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="536d6-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
