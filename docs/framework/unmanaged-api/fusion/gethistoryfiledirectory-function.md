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
ms.openlocfilehash: 10eead2772a2bbd8abaf7b9c090a091687725972
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778656"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="c8de9-102">GetHistoryFileDirectory 関数</span><span class="sxs-lookup"><span data-stu-id="c8de9-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="c8de9-103">アプリケーション履歴ディレクトリのパスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c8de9-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8de9-104">構文</span><span class="sxs-lookup"><span data-stu-id="c8de9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8de9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c8de9-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="c8de9-106">[out]アプリケーション履歴ディレクトリへのパスを保持するバッファー。</span><span class="sxs-lookup"><span data-stu-id="c8de9-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="c8de9-107">[入力、出力]バッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="c8de9-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8de9-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="c8de9-108">Return Value</span></span>  
 <span data-ttu-id="c8de9-109">このメソッドは、次の値だけでなく、WinError.h ファイルで定義されている標準の COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="c8de9-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="c8de9-110">リターン コード</span><span class="sxs-lookup"><span data-stu-id="c8de9-110">Return code</span></span>|<span data-ttu-id="c8de9-111">説明</span><span class="sxs-lookup"><span data-stu-id="c8de9-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c8de9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8de9-112">S_OK</span></span>|<span data-ttu-id="c8de9-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="c8de9-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="c8de9-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c8de9-114">E_INVALIDARG</span></span>|<span data-ttu-id="c8de9-115">`wzDir` または`pdwSize`が null の場合、または、バージョン文字列が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="c8de9-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8de9-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8de9-116">Remarks</span></span>  
 <span data-ttu-id="c8de9-117">正常に完了、`pdwSize`引数パス文字列の長さを設定します。</span><span class="sxs-lookup"><span data-stu-id="c8de9-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8de9-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="c8de9-118">Requirements</span></span>  
 <span data-ttu-id="c8de9-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8de9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8de9-120">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c8de9-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c8de9-121">**ライブラリ:** Fusion.dll と Mscorwks.dll します。</span><span class="sxs-lookup"><span data-stu-id="c8de9-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="c8de9-122">Mscorwks.dll のではなく Fusion.dll を使用して、正しいバージョンの .NET Framework を対象にすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c8de9-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="c8de9-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8de9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8de9-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8de9-124">See also</span></span>

- [<span data-ttu-id="c8de9-125">CreateHistoryReader 関数</span><span class="sxs-lookup"><span data-stu-id="c8de9-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="c8de9-126">NukeDownloadedCache 関数</span><span class="sxs-lookup"><span data-stu-id="c8de9-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)
- [<span data-ttu-id="c8de9-127">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="c8de9-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
