---
title: ICLRErrorReportingManager::GetBucketParametersForCurrentException メソッド
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
ms.openlocfilehash: b24f8ed4f5e2c6e0022f5599f2ab8c44a30a561a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129274"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="756d4-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="756d4-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="756d4-103">呼び出し元のスレッドで現在の例外の Watson バケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="756d4-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="756d4-104">*バケット*は、同じコード障害に関連するエラーデータのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="756d4-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="756d4-105">*Watson*は、例外に関連付けられているデータを収集および分析するための一連のテクノロジを指します。</span><span class="sxs-lookup"><span data-stu-id="756d4-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="756d4-106">構文</span><span class="sxs-lookup"><span data-stu-id="756d4-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="756d4-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="756d4-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="756d4-108">入出力例外のエラーデータを格納している[BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md)構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="756d4-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="756d4-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="756d4-109">Requirements</span></span>  
 <span data-ttu-id="756d4-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="756d4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="756d4-111">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="756d4-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="756d4-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="756d4-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="756d4-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="756d4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="756d4-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="756d4-114">See also</span></span>

- [<span data-ttu-id="756d4-115">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="756d4-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
