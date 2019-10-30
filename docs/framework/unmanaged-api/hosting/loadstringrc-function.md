---
title: LoadStringRC 関数
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
ms.openlocfilehash: 66d4c14234c7929af443922f86098b46a4aa6eb7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122013"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="d3d08-102">LoadStringRC 関数</span><span class="sxs-lookup"><span data-stu-id="d3d08-102">LoadStringRC Function</span></span>
<span data-ttu-id="d3d08-103">現在のスレッドの既定のカルチャを使用して、HRESULT 値をエラー メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="d3d08-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="d3d08-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="d3d08-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3d08-105">構文</span><span class="sxs-lookup"><span data-stu-id="d3d08-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3d08-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d3d08-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="d3d08-107">からHRESULT。</span><span class="sxs-lookup"><span data-stu-id="d3d08-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="d3d08-108">入出力正常に完了したときのエラーメッセージを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="d3d08-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="d3d08-109">からエラーメッセージバッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="d3d08-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="d3d08-110">から無効.</span><span class="sxs-lookup"><span data-stu-id="d3d08-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3d08-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="d3d08-111">Return Value</span></span>  
 <span data-ttu-id="d3d08-112">このメソッドは、次の値に加えて、Winerror.h で定義されている標準のコンポーネントオブジェクトモデル (COM) エラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="d3d08-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="d3d08-113">リターン コード</span><span class="sxs-lookup"><span data-stu-id="d3d08-113">Return code</span></span>|<span data-ttu-id="d3d08-114">説明</span><span class="sxs-lookup"><span data-stu-id="d3d08-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d3d08-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3d08-115">S_OK</span></span>|<span data-ttu-id="d3d08-116">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="d3d08-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="d3d08-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d3d08-117">E_INVALIDARG</span></span>|<span data-ttu-id="d3d08-118">`szBuffer` が null であるか、`iMax` がゼロ (0) です。</span><span class="sxs-lookup"><span data-stu-id="d3d08-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3d08-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="d3d08-119">Remarks</span></span>  
 <span data-ttu-id="d3d08-120">メソッドが正常に完了しなかった場合、`szBuffer` には空の文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d3d08-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3d08-121">［要件］</span><span class="sxs-lookup"><span data-stu-id="d3d08-121">Requirements</span></span>  
 <span data-ttu-id="d3d08-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d08-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3d08-123">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d3d08-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3d08-124">**ライブラリ:** Mscoree.dll と Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="d3d08-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="d3d08-125">Mscorwks.dll の代わりに Mscoree.dll を使用して、.NET Framework の正しいバージョンをターゲットにするようにしてください。</span><span class="sxs-lookup"><span data-stu-id="d3d08-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="d3d08-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3d08-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3d08-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3d08-127">See also</span></span>

- [<span data-ttu-id="d3d08-128">LoadStringRCEx 関数</span><span class="sxs-lookup"><span data-stu-id="d3d08-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="d3d08-129">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="d3d08-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
