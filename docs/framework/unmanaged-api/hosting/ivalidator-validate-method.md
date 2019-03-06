---
title: IValidator::Validate メソッド
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c362b41d842fb9d35cc7ae9293e2e305b2af281
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500435"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="fe510-102">IValidator::Validate メソッド</span><span class="sxs-lookup"><span data-stu-id="fe510-102">IValidator::Validate Method</span></span>
<span data-ttu-id="fe510-103">指定したポータブル実行可能 (PE) または Microsoft intermediate language (MSIL) ファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="fe510-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe510-104">構文</span><span class="sxs-lookup"><span data-stu-id="fe510-104">Syntax</span></span>  
  
```  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe510-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe510-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="fe510-106">[in]ポインター、`IVEHandler`検証エラーを処理するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="fe510-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="fe510-107">[in]ファイルが読み込まれているアプリケーション ドメインへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fe510-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="fe510-108">[in]ビットごとの組み合わせ[ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)実行される検証を示す値。</span><span class="sxs-lookup"><span data-stu-id="fe510-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="fe510-109">[in]検証を終了する前に許可されるエラーの最大数。</span><span class="sxs-lookup"><span data-stu-id="fe510-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="fe510-110">[in]使用されません。</span><span class="sxs-lookup"><span data-stu-id="fe510-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="fe510-111">[in]検証するファイルの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="fe510-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="fe510-112">[in]ファイルが格納されているメモリ バッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fe510-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="fe510-113">[in]検証するファイルのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="fe510-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe510-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="fe510-114">Requirements</span></span>  
 <span data-ttu-id="fe510-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe510-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe510-116">**ヘッダー:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="fe510-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="fe510-117">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="fe510-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe510-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe510-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe510-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe510-119">See also</span></span>

