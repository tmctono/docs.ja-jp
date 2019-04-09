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
ms.openlocfilehash: 5d4723fbf2311316184cb77c90754d7e037badcd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089592"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="34d19-102">GetRealProcAddress 関数</span><span class="sxs-lookup"><span data-stu-id="34d19-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="34d19-103">共通言語ランタイム (CLR) のインストールされている最新のバージョンからエクスポートされる、指定された関数のアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="34d19-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="34d19-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="34d19-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34d19-105">構文</span><span class="sxs-lookup"><span data-stu-id="34d19-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34d19-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34d19-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="34d19-107">[in]関数の名前。</span><span class="sxs-lookup"><span data-stu-id="34d19-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="34d19-108">[out]関数のアドレスへのポインターを受け取る場所。</span><span class="sxs-lookup"><span data-stu-id="34d19-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34d19-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="34d19-109">Return Value</span></span>  
 <span data-ttu-id="34d19-110">このメソッドは、CorError.h で定義されている次の値だけでなく、WinError.h で定義されている標準のコンポーネント オブジェクト モデル (COM) エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="34d19-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="34d19-111">リターン コード</span><span class="sxs-lookup"><span data-stu-id="34d19-111">Return code</span></span>|<span data-ttu-id="34d19-112">説明</span><span class="sxs-lookup"><span data-stu-id="34d19-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="34d19-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="34d19-113">S_OK</span></span>|<span data-ttu-id="34d19-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="34d19-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="34d19-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="34d19-115">E_POINTER</span></span>|`ppv` <span data-ttu-id="34d19-116">無効です。</span><span class="sxs-lookup"><span data-stu-id="34d19-116">is not valid.</span></span>|  
|<span data-ttu-id="34d19-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="34d19-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="34d19-118">関数は、ランタイムからはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="34d19-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="34d19-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="34d19-119">Requirements</span></span>  
 <span data-ttu-id="34d19-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34d19-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34d19-121">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="34d19-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34d19-122">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="34d19-122">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="34d19-123">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="34d19-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="34d19-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="34d19-124">See also</span></span>

- [<span data-ttu-id="34d19-125">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="34d19-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
