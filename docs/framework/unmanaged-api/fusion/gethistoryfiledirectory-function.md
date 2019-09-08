---
title: GetHistoryFileDirectory 関数
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: adbbf94dc36c6d82360ed532b283cd666a1a52ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796849"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="2bc1c-102">GetHistoryFileDirectory 関数</span><span class="sxs-lookup"><span data-stu-id="2bc1c-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="2bc1c-103">アプリケーション履歴ディレクトリのパスを取得します。</span><span class="sxs-lookup"><span data-stu-id="2bc1c-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bc1c-104">構文</span><span class="sxs-lookup"><span data-stu-id="2bc1c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bc1c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2bc1c-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="2bc1c-106">入出力アプリケーション履歴ディレクトリへのパスを保持するバッファー。</span><span class="sxs-lookup"><span data-stu-id="2bc1c-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="2bc1c-107">[入力、出力]バッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="2bc1c-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bc1c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="2bc1c-108">Return Value</span></span>  
 <span data-ttu-id="2bc1c-109">このメソッドは、Winerror.h ファイルで定義されているように、次の値に加えて、標準の COM エラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="2bc1c-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="2bc1c-110">リターン コード</span><span class="sxs-lookup"><span data-stu-id="2bc1c-110">Return code</span></span>|<span data-ttu-id="2bc1c-111">説明</span><span class="sxs-lookup"><span data-stu-id="2bc1c-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="2bc1c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2bc1c-112">S_OK</span></span>|<span data-ttu-id="2bc1c-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="2bc1c-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="2bc1c-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2bc1c-114">E_INVALIDARG</span></span>|<span data-ttu-id="2bc1c-115">`wzDir`また`pdwSize`はが null であるか、またはバージョン文字列が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="2bc1c-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bc1c-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="2bc1c-116">Remarks</span></span>  
 <span data-ttu-id="2bc1c-117">正常に完了する`pdwSize`と、引数はパス文字列の長さに設定されます。</span><span class="sxs-lookup"><span data-stu-id="2bc1c-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bc1c-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="2bc1c-118">Requirements</span></span>  
 <span data-ttu-id="2bc1c-119">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bc1c-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bc1c-120">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2bc1c-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2bc1c-121">**ライブラリ**Fusion .dll と Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="2bc1c-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="2bc1c-122">Mscorwks.dll の代わりに Fusion を使用して、正しいバージョンの .NET Framework を対象としていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2bc1c-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="2bc1c-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bc1c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc1c-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bc1c-124">See also</span></span>

- [<span data-ttu-id="2bc1c-125">CreateHistoryReader 関数</span><span class="sxs-lookup"><span data-stu-id="2bc1c-125">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="2bc1c-126">NukeDownloadedCache 関数</span><span class="sxs-lookup"><span data-stu-id="2bc1c-126">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)
- [<span data-ttu-id="2bc1c-127">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="2bc1c-127">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
