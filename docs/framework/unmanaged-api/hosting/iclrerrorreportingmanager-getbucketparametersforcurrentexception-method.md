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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 276a69deecccc91b3c511403c2bd0d5c0baabd9d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772806"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="4459d-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="4459d-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="4459d-103">呼び出し元のスレッドで現在の例外のワトソン バケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="4459d-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="4459d-104">A*バケット*は同じコードの欠陥に関連するエラー データのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="4459d-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="4459d-105">*ワトソン博士*例外に関連付けられているデータ収集および分析のためのテクノロジのセットを指します。</span><span class="sxs-lookup"><span data-stu-id="4459d-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4459d-106">構文</span><span class="sxs-lookup"><span data-stu-id="4459d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4459d-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4459d-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="4459d-108">[out]ポインターを[BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md)例外のエラー データを含む構造体。</span><span class="sxs-lookup"><span data-stu-id="4459d-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4459d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="4459d-109">Requirements</span></span>  
 <span data-ttu-id="4459d-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4459d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4459d-111">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4459d-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4459d-112">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="4459d-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4459d-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4459d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4459d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4459d-114">See also</span></span>

- [<span data-ttu-id="4459d-115">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4459d-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
