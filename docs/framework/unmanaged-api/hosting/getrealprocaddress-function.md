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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 40cd5b6298012ef4dc21987a2a2dbe95c02a0ff2
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490354"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="ea110-102">GetRealProcAddress 関数</span><span class="sxs-lookup"><span data-stu-id="ea110-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="ea110-103">共通言語ランタイム (CLR) のインストールされている最新のバージョンからエクスポートされる、指定された関数のアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="ea110-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="ea110-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="ea110-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea110-105">構文</span><span class="sxs-lookup"><span data-stu-id="ea110-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea110-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea110-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="ea110-107">[in]関数の名前。</span><span class="sxs-lookup"><span data-stu-id="ea110-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="ea110-108">[out]関数のアドレスへのポインターを受け取る場所。</span><span class="sxs-lookup"><span data-stu-id="ea110-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea110-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="ea110-109">Return Value</span></span>  
 <span data-ttu-id="ea110-110">このメソッドは、CorError.h で定義されている次の値だけでなく、WinError.h で定義されている標準のコンポーネント オブジェクト モデル (COM) エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="ea110-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="ea110-111">リターン コード</span><span class="sxs-lookup"><span data-stu-id="ea110-111">Return code</span></span>|<span data-ttu-id="ea110-112">説明</span><span class="sxs-lookup"><span data-stu-id="ea110-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ea110-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea110-113">S_OK</span></span>|<span data-ttu-id="ea110-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="ea110-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="ea110-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ea110-115">E_POINTER</span></span>|<span data-ttu-id="ea110-116">`ppv` が無効です。</span><span class="sxs-lookup"><span data-stu-id="ea110-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="ea110-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="ea110-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="ea110-118">関数は、ランタイムからはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="ea110-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea110-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="ea110-119">Requirements</span></span>  
 <span data-ttu-id="ea110-120">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea110-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea110-121">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ea110-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea110-122">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea110-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea110-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea110-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea110-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea110-124">See also</span></span>

- [<span data-ttu-id="ea110-125">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="ea110-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
