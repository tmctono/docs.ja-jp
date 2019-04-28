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
ms.openlocfilehash: 35faeb69e864a428dc40394ad89a7d50b95bbcab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757665"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="d2580-102">IInstallReferenceEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d2580-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="d2580-103">グローバル アセンブリ キャッシュにインストールされている参照先アセンブリの列挙子を表します。</span><span class="sxs-lookup"><span data-stu-id="d2580-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2580-104">構文</span><span class="sxs-lookup"><span data-stu-id="d2580-104">Syntax</span></span>  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d2580-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d2580-105">Methods</span></span>  
  
|<span data-ttu-id="d2580-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="d2580-106">Method</span></span>|<span data-ttu-id="d2580-107">説明</span><span class="sxs-lookup"><span data-stu-id="d2580-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d2580-108">GetNextInstallReferenceItem メソッド</span><span class="sxs-lookup"><span data-stu-id="d2580-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="d2580-109">次のポインターを取得`IInstallReferenceItem`これに含まれる`IInstallReferenceEnum`します。</span><span class="sxs-lookup"><span data-stu-id="d2580-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2580-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="d2580-110">Requirements</span></span>  
 <span data-ttu-id="d2580-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2580-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2580-112">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d2580-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d2580-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2580-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2580-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2580-114">See also</span></span>

- [<span data-ttu-id="d2580-115">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d2580-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="d2580-116">IInstallReferenceItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d2580-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
