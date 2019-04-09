---
title: CallFunctionShim 関数
ms.date: 03/30/2017
api_name:
- CallFunctionShim
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CallFunctionShim
helpviewer_keywords:
- CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7aeb813cafbf5b18739c4574c386398ac3c7a77b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180480"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="c2640-102">CallFunctionShim 関数</span><span class="sxs-lookup"><span data-stu-id="c2640-102">CallFunctionShim Function</span></span>
<span data-ttu-id="c2640-103">指定したライブラリ内の関数を、名前とパラメーターを指定して呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c2640-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="c2640-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="c2640-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2640-105">構文</span><span class="sxs-lookup"><span data-stu-id="c2640-105">Syntax</span></span>  
  
```  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2640-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2640-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="c2640-107">[in]関数を含むライブラリの名前。</span><span class="sxs-lookup"><span data-stu-id="c2640-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="c2640-108">[in]関数の名前。</span><span class="sxs-lookup"><span data-stu-id="c2640-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="c2640-109">[in]関数に渡す最初の引数。</span><span class="sxs-lookup"><span data-stu-id="c2640-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="c2640-110">[in]関数に渡す 2 番目の引数。</span><span class="sxs-lookup"><span data-stu-id="c2640-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="c2640-111">[in]関数を含むライブラリのバージョン。</span><span class="sxs-lookup"><span data-stu-id="c2640-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="c2640-112">[in]将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="c2640-112">[in] Reserved for future use.</span></span> <span data-ttu-id="c2640-113">このパラメーターに 0 を渡します。</span><span class="sxs-lookup"><span data-stu-id="c2640-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2640-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="c2640-114">Requirements</span></span>  
 <span data-ttu-id="c2640-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2640-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2640-116">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2640-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2640-117">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2640-117">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c2640-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c2640-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c2640-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2640-119">See also</span></span>

- [<span data-ttu-id="c2640-120">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="c2640-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
