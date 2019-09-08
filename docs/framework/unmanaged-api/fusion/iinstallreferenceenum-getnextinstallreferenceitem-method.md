---
title: IInstallReferenceEnum::GetNextInstallReferenceItem メソッド
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20e2bff4257df64f761fd8fff880643d4e786748
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796445"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="d653d-102">IInstallReferenceEnum::GetNextInstallReferenceItem メソッド</span><span class="sxs-lookup"><span data-stu-id="d653d-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="d653d-103">この[Iinstallreferenceitem](iinstallreferenceenum-interface.md)オブジェクトに格納されている次の[Iinstallreferenceitem](iinstallreferenceitem-interface.md)オブジェクトへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="d653d-103">Gets a pointer to the next [IInstallReferenceItem](iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d653d-104">構文</span><span class="sxs-lookup"><span data-stu-id="d653d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d653d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d653d-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="d653d-106">入出力返され`IInstallReferenceItem`たポインター。</span><span class="sxs-lookup"><span data-stu-id="d653d-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d653d-107">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="d653d-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="d653d-108">`dwFlags`0 (ゼロ) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d653d-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="d653d-109">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="d653d-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="d653d-110">`pvReserved`null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d653d-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d653d-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d653d-111">Requirements</span></span>  
 <span data-ttu-id="d653d-112">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d653d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d653d-113">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d653d-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d653d-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d653d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d653d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d653d-115">See also</span></span>

- [<span data-ttu-id="d653d-116">IInstallReferenceItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d653d-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="d653d-117">IInstallReferenceEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d653d-117">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
