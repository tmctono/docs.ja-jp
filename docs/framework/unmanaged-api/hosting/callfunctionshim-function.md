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
ms.openlocfilehash: d39e15a2ba71ba0c0147482259f5618dcb5d298b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192091"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="1c49e-102">CallFunctionShim 関数</span><span class="sxs-lookup"><span data-stu-id="1c49e-102">CallFunctionShim Function</span></span>
<span data-ttu-id="1c49e-103">指定したライブラリ内の関数を、名前とパラメーターを指定して呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1c49e-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="1c49e-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="1c49e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c49e-105">構文</span><span class="sxs-lookup"><span data-stu-id="1c49e-105">Syntax</span></span>  
  
```cpp  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c49e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1c49e-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="1c49e-107">から関数を格納しているライブラリの名前。</span><span class="sxs-lookup"><span data-stu-id="1c49e-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="1c49e-108">から関数の名前。</span><span class="sxs-lookup"><span data-stu-id="1c49e-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="1c49e-109">から関数に渡す1番目の引数。</span><span class="sxs-lookup"><span data-stu-id="1c49e-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="1c49e-110">から関数に渡す2番目の引数。</span><span class="sxs-lookup"><span data-stu-id="1c49e-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="1c49e-111">から関数が含まれているライブラリのバージョン。</span><span class="sxs-lookup"><span data-stu-id="1c49e-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="1c49e-112">から将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1c49e-112">[in] Reserved for future use.</span></span> <span data-ttu-id="1c49e-113">このパラメーターに0を渡します。</span><span class="sxs-lookup"><span data-stu-id="1c49e-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c49e-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="1c49e-114">Requirements</span></span>  
 <span data-ttu-id="1c49e-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c49e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c49e-116">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1c49e-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c49e-117">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1c49e-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c49e-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c49e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c49e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c49e-119">See also</span></span>

- [<span data-ttu-id="1c49e-120">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="1c49e-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
