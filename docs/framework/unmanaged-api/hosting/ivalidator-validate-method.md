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
ms.openlocfilehash: 8ae47eac713fbee30ea543538957b12460b8e1fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123280"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="a095e-102">IValidator::Validate メソッド</span><span class="sxs-lookup"><span data-stu-id="a095e-102">IValidator::Validate Method</span></span>
<span data-ttu-id="a095e-103">指定された移植可能な実行可能 (PE) ファイルまたは MSIL (Microsoft 中間言語) ファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="a095e-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a095e-104">構文</span><span class="sxs-lookup"><span data-stu-id="a095e-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="a095e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a095e-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="a095e-106">から検証エラーを処理する `IVEHandler` インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a095e-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="a095e-107">からファイルが読み込まれるアプリケーションドメインへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a095e-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="a095e-108">から実行する必要のある検証を示す、 [Validatorflags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="a095e-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="a095e-109">から検証を終了するまでに許容されるエラーの最大数。</span><span class="sxs-lookup"><span data-stu-id="a095e-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="a095e-110">から使用しません。</span><span class="sxs-lookup"><span data-stu-id="a095e-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="a095e-111">から検証するファイルの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="a095e-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="a095e-112">からファイルが格納されているメモリバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a095e-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="a095e-113">から検証するファイルのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="a095e-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a095e-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="a095e-114">Requirements</span></span>  
 <span data-ttu-id="a095e-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a095e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a095e-116">**ヘッダー:** IValidator、IValidator</span><span class="sxs-lookup"><span data-stu-id="a095e-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="a095e-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a095e-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a095e-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a095e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
