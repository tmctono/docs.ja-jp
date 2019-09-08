---
title: IInstallReferenceEnum インターフェイス
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum
helpviewer_keywords:
- IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d29b9e2a9b9022f682065816a62734d6c5b2d62
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796411"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="5761f-102">IInstallReferenceEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5761f-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="5761f-103">グローバルアセンブリキャッシュにインストールされている参照アセンブリの列挙子を表します。</span><span class="sxs-lookup"><span data-stu-id="5761f-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5761f-104">構文</span><span class="sxs-lookup"><span data-stu-id="5761f-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5761f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5761f-105">Methods</span></span>  
  
|<span data-ttu-id="5761f-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="5761f-106">Method</span></span>|<span data-ttu-id="5761f-107">説明</span><span class="sxs-lookup"><span data-stu-id="5761f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5761f-108">GetNextInstallReferenceItem メソッド</span><span class="sxs-lookup"><span data-stu-id="5761f-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="5761f-109">`IInstallReferenceItem` この`IInstallReferenceEnum`に格納されている次のへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5761f-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5761f-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="5761f-110">Requirements</span></span>  
 <span data-ttu-id="5761f-111">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5761f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5761f-112">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5761f-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5761f-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5761f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5761f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5761f-114">See also</span></span>

- [<span data-ttu-id="5761f-115">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5761f-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="5761f-116">IInstallReferenceItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5761f-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
