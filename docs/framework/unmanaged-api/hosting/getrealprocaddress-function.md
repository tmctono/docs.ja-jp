---
title: GetRealProcAddress 関数
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
ms.openlocfilehash: 4c914e00987053b1c1e9e00bf8e54632175e1de8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178161"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="c3b0d-102">GetRealProcAddress 関数</span><span class="sxs-lookup"><span data-stu-id="c3b0d-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="c3b0d-103">インストールされている共通言語ランタイム (CLR) の最新バージョンからエクスポートされた、指定した関数のアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c3b0d-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="c3b0d-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c3b0d-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b0d-105">構文</span><span class="sxs-lookup"><span data-stu-id="c3b0d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3b0d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3b0d-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="c3b0d-107">[in]関数の名前。</span><span class="sxs-lookup"><span data-stu-id="c3b0d-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="c3b0d-108">[アウト]関数のアドレスへのポインターを受け取る場所。</span><span class="sxs-lookup"><span data-stu-id="c3b0d-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3b0d-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="c3b0d-109">Return Value</span></span>  
 <span data-ttu-id="c3b0d-110">このメソッドは、CorError.h で定義されている次の値に加えて、WinError.h で定義されている標準のコンポーネント オブジェクト モデル (COM) エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="c3b0d-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="c3b0d-111">リターン コード</span><span class="sxs-lookup"><span data-stu-id="c3b0d-111">Return code</span></span>|<span data-ttu-id="c3b0d-112">説明</span><span class="sxs-lookup"><span data-stu-id="c3b0d-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c3b0d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3b0d-113">S_OK</span></span>|<span data-ttu-id="c3b0d-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="c3b0d-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="c3b0d-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="c3b0d-115">E_POINTER</span></span>|<span data-ttu-id="c3b0d-116">`ppv` が無効です。</span><span class="sxs-lookup"><span data-stu-id="c3b0d-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="c3b0d-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="c3b0d-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="c3b0d-118">関数はランタイムからエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="c3b0d-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3b0d-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="c3b0d-119">Requirements</span></span>  
 <span data-ttu-id="c3b0d-120">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3b0d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3b0d-121">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c3b0d-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3b0d-122">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c3b0d-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3b0d-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3b0d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b0d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3b0d-124">See also</span></span>

- [<span data-ttu-id="c3b0d-125">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="c3b0d-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
