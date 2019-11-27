---
title: IMetaDataValidate::ValidatorInit メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
ms.openlocfilehash: 165a57d8029fe03b9de3754fcf7c4db757292cec
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443606"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="acf1b-102">IMetaDataValidate::ValidatorInit メソッド</span><span class="sxs-lookup"><span data-stu-id="acf1b-102">IMetaDataValidate::ValidatorInit Method</span></span>
<span data-ttu-id="acf1b-103">現在のメタデータ スコープ内にあるモジュールの種類を指定するフラグを設定し、指定されたコールバック メソッドを検証エラー用に登録します。</span><span class="sxs-lookup"><span data-stu-id="acf1b-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acf1b-104">構文</span><span class="sxs-lookup"><span data-stu-id="acf1b-104">Syntax</span></span>  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acf1b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="acf1b-105">Parameters</span></span>  
 `dwModule`  
 <span data-ttu-id="acf1b-106">から現在のメタデータスコープ内のモジュールの型を指定する[Corvalidatormoduletype](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="acf1b-106">[in] A value of the [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="acf1b-107">から検証エラーの関数コールバックとして機能する[IUnknown](/cpp/atl/iunknown)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="acf1b-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acf1b-108">要件</span><span class="sxs-lookup"><span data-stu-id="acf1b-108">Requirements</span></span>  
 <span data-ttu-id="acf1b-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acf1b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acf1b-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="acf1b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="acf1b-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="acf1b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="acf1b-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acf1b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf1b-113">参照</span><span class="sxs-lookup"><span data-stu-id="acf1b-113">See also</span></span>

- [<span data-ttu-id="acf1b-114">IMetaDataValidate インターフェイス</span><span class="sxs-lookup"><span data-stu-id="acf1b-114">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)
