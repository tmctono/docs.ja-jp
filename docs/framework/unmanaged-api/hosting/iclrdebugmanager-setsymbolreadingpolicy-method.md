---
title: ICLRDebugManager::SetSymbolReadingPolicy メソッド
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetSymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type:
- apiref
ms.openlocfilehash: f037e902a9f573023022c81503ea3b987cf6d424
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615759"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="58c0f-102">ICLRDebugManager::SetSymbolReadingPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="58c0f-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="58c0f-103">プログラムデータベース (PDB) ファイルを読み取るためのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="58c0f-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="58c0f-104">ポリシーは、行番号とファイルに関する情報が呼び出し履歴に含まれるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="58c0f-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c0f-105">構文</span><span class="sxs-lookup"><span data-stu-id="58c0f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58c0f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="58c0f-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="58c0f-107">から[ESymbolReadingPolicy](esymbolreadingpolicy-enumeration.md)列挙体のメンバー。</span><span class="sxs-lookup"><span data-stu-id="58c0f-107">[in] A member of the [ESymbolReadingPolicy](esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58c0f-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="58c0f-108">Return Value</span></span>  
  
|<span data-ttu-id="58c0f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58c0f-109">HRESULT</span></span>|<span data-ttu-id="58c0f-110">説明</span><span class="sxs-lookup"><span data-stu-id="58c0f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="58c0f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="58c0f-111">S_OK</span></span>|<span data-ttu-id="58c0f-112">`SetSymbolReadingPolicy`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="58c0f-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="58c0f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="58c0f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="58c0f-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="58c0f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="58c0f-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="58c0f-115">E_FAIL</span></span>|<span data-ttu-id="58c0f-116">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="58c0f-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="58c0f-117">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="58c0f-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="58c0f-118">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="58c0f-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58c0f-119">要件</span><span class="sxs-lookup"><span data-stu-id="58c0f-119">Requirements</span></span>  
 <span data-ttu-id="58c0f-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58c0f-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58c0f-121">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="58c0f-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58c0f-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="58c0f-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58c0f-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58c0f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c0f-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="58c0f-124">See also</span></span>

- [<span data-ttu-id="58c0f-125">ICLRDebugManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58c0f-125">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
