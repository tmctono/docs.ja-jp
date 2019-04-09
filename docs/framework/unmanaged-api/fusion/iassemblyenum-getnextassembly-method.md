---
title: IAssemblyEnum::GetNextAssembly メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a77e468363b59e76e55aa24d97d064189ad297e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117750"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="ce97f-102">IAssemblyEnum::GetNextAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="ce97f-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="ce97f-103">次のポインターを取得[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)これに含まれる[IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ce97f-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce97f-104">構文</span><span class="sxs-lookup"><span data-stu-id="ce97f-104">Syntax</span></span>  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce97f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ce97f-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="ce97f-106">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="ce97f-106">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="ce97f-107">null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce97f-107">must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="ce97f-108">[out]返された`IAssemblyName`ポインター。</span><span class="sxs-lookup"><span data-stu-id="ce97f-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ce97f-109">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="ce97f-109">[in] Reserved for future extensibility.</span></span> `dwFlags` <span data-ttu-id="ce97f-110">0 (ゼロ) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce97f-110">must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce97f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="ce97f-111">Requirements</span></span>  
 <span data-ttu-id="ce97f-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce97f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce97f-113">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ce97f-113">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="ce97f-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="ce97f-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ce97f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce97f-115">See also</span></span>

- [<span data-ttu-id="ce97f-116">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce97f-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="ce97f-117">IAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce97f-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
