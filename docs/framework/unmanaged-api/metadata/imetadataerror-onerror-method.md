---
title: IMetaDataError::OnError メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataError.OnError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type:
- apiref
ms.openlocfilehash: 489fa217744e41ccb5d27d088790131c15e1ee52
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177399"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="2880d-102">IMetaDataError::OnError メソッド</span><span class="sxs-lookup"><span data-stu-id="2880d-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="2880d-103">メタデータのマージ中に発生したエラーを通知します。</span><span class="sxs-lookup"><span data-stu-id="2880d-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2880d-104">構文</span><span class="sxs-lookup"><span data-stu-id="2880d-104">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2880d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2880d-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="2880d-106">[in]呼び出し元のメソッドに返される HRESULT エラー値。</span><span class="sxs-lookup"><span data-stu-id="2880d-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="2880d-107">[in]エラーの発生時にマージされていたコード オブジェクトのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="2880d-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2880d-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="2880d-108">Requirements</span></span>  
 <span data-ttu-id="2880d-109">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2880d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2880d-110">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="2880d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2880d-111">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="2880d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2880d-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2880d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2880d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2880d-113">See also</span></span>

- [<span data-ttu-id="2880d-114">IMetaDataError インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2880d-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
