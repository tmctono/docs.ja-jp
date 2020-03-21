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
ms.openlocfilehash: 56ae7b7cf3b577bfe41ebd0bdd98e0da68047b44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176241"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="2bbdb-102">LoadStringRC 関数</span><span class="sxs-lookup"><span data-stu-id="2bbdb-102">LoadStringRC Function</span></span>
<span data-ttu-id="2bbdb-103">現在のスレッドの既定のカルチャを使用して、HRESULT 値をエラー メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="2bbdb-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bbdb-105">構文</span><span class="sxs-lookup"><span data-stu-id="2bbdb-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bbdb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2bbdb-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="2bbdb-107">[in]HRESULT。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="2bbdb-108">[アウト]正常終了時にエラー メッセージが格納されているバッファー。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="2bbdb-109">[in]エラー メッセージ バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="2bbdb-110">[in]無視。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bbdb-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="2bbdb-111">Return Value</span></span>  
 <span data-ttu-id="2bbdb-112">このメソッドは、WinError.h で定義されている次の値に加えて、標準のコンポーネント オブジェクト モデル (COM) エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="2bbdb-113">リターン コード</span><span class="sxs-lookup"><span data-stu-id="2bbdb-113">Return code</span></span>|<span data-ttu-id="2bbdb-114">説明</span><span class="sxs-lookup"><span data-stu-id="2bbdb-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="2bbdb-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="2bbdb-115">S_OK</span></span>|<span data-ttu-id="2bbdb-116">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="2bbdb-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2bbdb-117">E_INVALIDARG</span></span>|<span data-ttu-id="2bbdb-118">`szBuffer`が null`iMax`であるか、ゼロ (0) です。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bbdb-119">解説</span><span class="sxs-lookup"><span data-stu-id="2bbdb-119">Remarks</span></span>  
 <span data-ttu-id="2bbdb-120">メソッドが正常に完了しなかった場合は、`szBuffer`空の文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bbdb-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="2bbdb-121">Requirements</span></span>  
 <span data-ttu-id="2bbdb-122">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bbdb-123">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2bbdb-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2bbdb-124">**ライブラリ:** MSCorEE.dll と Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="2bbdb-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="2bbdb-125">Mscorwks.dll の代わりに MSCorEE.dll を使用して、.NET Framework の正しいバージョンを対象にしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="2bbdb-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bbdb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bbdb-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bbdb-127">See also</span></span>

- [<span data-ttu-id="2bbdb-128">LoadStringRCEx 関数</span><span class="sxs-lookup"><span data-stu-id="2bbdb-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="2bbdb-129">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="2bbdb-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
