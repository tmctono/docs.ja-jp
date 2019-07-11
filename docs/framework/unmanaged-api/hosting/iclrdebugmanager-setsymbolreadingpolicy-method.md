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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2921484cb2baa92593ddb0335cf7b20c5c0f33eb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773006"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="200ec-102">ICLRDebugManager::SetSymbolReadingPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="200ec-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="200ec-103">プログラム データベース (PDB) ファイルを読み取るためのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="200ec-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="200ec-104">ポリシーは、呼び出し履歴で行番号およびファイルに関する情報が含まれているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="200ec-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="200ec-105">構文</span><span class="sxs-lookup"><span data-stu-id="200ec-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="200ec-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="200ec-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="200ec-107">[in]メンバー、 [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="200ec-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="200ec-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="200ec-108">Return Value</span></span>  
  
|<span data-ttu-id="200ec-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="200ec-109">HRESULT</span></span>|<span data-ttu-id="200ec-110">説明</span><span class="sxs-lookup"><span data-stu-id="200ec-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="200ec-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="200ec-111">S_OK</span></span>|<span data-ttu-id="200ec-112">`SetSymbolReadingPolicy` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="200ec-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="200ec-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="200ec-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="200ec-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="200ec-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="200ec-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="200ec-115">E_FAIL</span></span>|<span data-ttu-id="200ec-116">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="200ec-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="200ec-117">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="200ec-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="200ec-118">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="200ec-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="200ec-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="200ec-119">Requirements</span></span>  
 <span data-ttu-id="200ec-120">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="200ec-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="200ec-121">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="200ec-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="200ec-122">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="200ec-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="200ec-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="200ec-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="200ec-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="200ec-124">See also</span></span>

- [<span data-ttu-id="200ec-125">ICLRDebugManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="200ec-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
