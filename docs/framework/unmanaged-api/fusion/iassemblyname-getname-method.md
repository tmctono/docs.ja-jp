---
title: IAssemblyName::GetName メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
ms.openlocfilehash: 5f758d76d779cff7db119e69dc1cf3342071f1c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134348"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="77db6-102">IAssemblyName::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="77db6-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="77db6-103">この[IAssemblyName](iassemblyname-interface.md)オブジェクトによって参照されるアセンブリの単純な、暗号化されていない名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="77db6-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77db6-104">構文</span><span class="sxs-lookup"><span data-stu-id="77db6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77db6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="77db6-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="77db6-106">[入力、出力]ワイド文字の `pwzName` のサイズ (null 終端文字を含む)。</span><span class="sxs-lookup"><span data-stu-id="77db6-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="77db6-107">入出力参照されたアセンブリの名前を保持するバッファー。</span><span class="sxs-lookup"><span data-stu-id="77db6-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77db6-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="77db6-108">Requirements</span></span>  
 <span data-ttu-id="77db6-109">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77db6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77db6-110">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="77db6-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="77db6-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77db6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77db6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="77db6-112">See also</span></span>

- [<span data-ttu-id="77db6-113">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77db6-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
