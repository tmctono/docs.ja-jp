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
ms.openlocfilehash: 6bbf8366054c58543444a4b710a687198f365e6e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617192"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="2adfc-102">GetRealProcAddress 関数</span><span class="sxs-lookup"><span data-stu-id="2adfc-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="2adfc-103">インストールされている最新バージョンの共通言語ランタイム (CLR) からエクスポートされた、指定された関数のアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="2adfc-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="2adfc-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="2adfc-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2adfc-105">構文</span><span class="sxs-lookup"><span data-stu-id="2adfc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2adfc-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2adfc-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="2adfc-107">から関数の名前。</span><span class="sxs-lookup"><span data-stu-id="2adfc-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="2adfc-108">入出力関数のアドレスへのポインターを受け取る位置。</span><span class="sxs-lookup"><span data-stu-id="2adfc-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2adfc-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="2adfc-109">Return Value</span></span>  
 <span data-ttu-id="2adfc-110">このメソッドは、Winerror.h で定義されているように、CorError. h で定義されている次の値に加えて、標準の Component Object Model (COM) エラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="2adfc-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="2adfc-111">リターン コード</span><span class="sxs-lookup"><span data-stu-id="2adfc-111">Return code</span></span>|<span data-ttu-id="2adfc-112">説明</span><span class="sxs-lookup"><span data-stu-id="2adfc-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="2adfc-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="2adfc-113">S_OK</span></span>|<span data-ttu-id="2adfc-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="2adfc-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="2adfc-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="2adfc-115">E_POINTER</span></span>|<span data-ttu-id="2adfc-116">`ppv` が無効です。</span><span class="sxs-lookup"><span data-stu-id="2adfc-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="2adfc-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="2adfc-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="2adfc-118">関数はランタイムからエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="2adfc-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2adfc-119">要件</span><span class="sxs-lookup"><span data-stu-id="2adfc-119">Requirements</span></span>  
 <span data-ttu-id="2adfc-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2adfc-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2adfc-121">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2adfc-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2adfc-122">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2adfc-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2adfc-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2adfc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2adfc-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="2adfc-124">See also</span></span>

- [<span data-ttu-id="2adfc-125">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="2adfc-125">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
