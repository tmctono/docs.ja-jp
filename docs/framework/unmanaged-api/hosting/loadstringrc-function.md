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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9047bf973224cdbc1f67463ef70f15f81089f827
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768456"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="91ad5-102">LoadStringRC 関数</span><span class="sxs-lookup"><span data-stu-id="91ad5-102">LoadStringRC Function</span></span>
<span data-ttu-id="91ad5-103">現在のスレッドの既定のカルチャを使用して、HRESULT 値をエラー メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="91ad5-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="91ad5-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="91ad5-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91ad5-105">構文</span><span class="sxs-lookup"><span data-stu-id="91ad5-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91ad5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91ad5-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="91ad5-107">[in]HRESULT。</span><span class="sxs-lookup"><span data-stu-id="91ad5-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="91ad5-108">[out]正常完了時にエラー メッセージを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="91ad5-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="91ad5-109">[in]エラー メッセージのバッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="91ad5-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="91ad5-110">[in]無視されます。</span><span class="sxs-lookup"><span data-stu-id="91ad5-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91ad5-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="91ad5-111">Return Value</span></span>  
 <span data-ttu-id="91ad5-112">このメソッドは、次の値だけでなく、WinError.h で定義されている標準のコンポーネント オブジェクト モデル (COM) エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="91ad5-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="91ad5-113">リターン コード</span><span class="sxs-lookup"><span data-stu-id="91ad5-113">Return code</span></span>|<span data-ttu-id="91ad5-114">説明</span><span class="sxs-lookup"><span data-stu-id="91ad5-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="91ad5-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="91ad5-115">S_OK</span></span>|<span data-ttu-id="91ad5-116">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="91ad5-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="91ad5-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="91ad5-117">E_INVALIDARG</span></span>|<span data-ttu-id="91ad5-118">`szBuffer` null または`iMax`はゼロ (0)。</span><span class="sxs-lookup"><span data-stu-id="91ad5-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91ad5-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="91ad5-119">Remarks</span></span>  
 <span data-ttu-id="91ad5-120">メソッドが正常に完了しない場合`szBuffer`空の文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="91ad5-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91ad5-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="91ad5-121">Requirements</span></span>  
 <span data-ttu-id="91ad5-122">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="91ad5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91ad5-123">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="91ad5-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91ad5-124">**ライブラリ:** MSCorEE.dll と Mscorwks.dll します。</span><span class="sxs-lookup"><span data-stu-id="91ad5-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="91ad5-125">Mscorwks.dll の代わりに MSCorEE.dll を使用して、正しいバージョンの .NET Framework を対象にすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="91ad5-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="91ad5-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91ad5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ad5-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="91ad5-127">See also</span></span>

- [<span data-ttu-id="91ad5-128">LoadStringRCEx 関数</span><span class="sxs-lookup"><span data-stu-id="91ad5-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="91ad5-129">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="91ad5-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
