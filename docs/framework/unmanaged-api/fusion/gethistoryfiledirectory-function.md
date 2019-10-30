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
ms.openlocfilehash: 1aabfad14ee2eb35916bbf115631602276cd1fc3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109890"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="6aabd-102">GetHistoryFileDirectory 関数</span><span class="sxs-lookup"><span data-stu-id="6aabd-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="6aabd-103">アプリケーション履歴ディレクトリのパスを取得します。</span><span class="sxs-lookup"><span data-stu-id="6aabd-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aabd-104">構文</span><span class="sxs-lookup"><span data-stu-id="6aabd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6aabd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6aabd-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="6aabd-106">入出力アプリケーション履歴ディレクトリへのパスを保持するバッファー。</span><span class="sxs-lookup"><span data-stu-id="6aabd-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="6aabd-107">[入力、出力]バッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="6aabd-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6aabd-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="6aabd-108">Return Value</span></span>  
 <span data-ttu-id="6aabd-109">このメソッドは、Winerror.h ファイルで定義されているように、次の値に加えて、標準の COM エラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="6aabd-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="6aabd-110">リターン コード</span><span class="sxs-lookup"><span data-stu-id="6aabd-110">Return code</span></span>|<span data-ttu-id="6aabd-111">説明</span><span class="sxs-lookup"><span data-stu-id="6aabd-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="6aabd-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6aabd-112">S_OK</span></span>|<span data-ttu-id="6aabd-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="6aabd-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="6aabd-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6aabd-114">E_INVALIDARG</span></span>|<span data-ttu-id="6aabd-115">`wzDir` または `pdwSize` が null であるか、バージョン文字列が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="6aabd-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6aabd-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="6aabd-116">Remarks</span></span>  
 <span data-ttu-id="6aabd-117">正常に完了すると、`pdwSize` の引数がパス文字列の長さに設定されます。</span><span class="sxs-lookup"><span data-stu-id="6aabd-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aabd-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="6aabd-118">Requirements</span></span>  
 <span data-ttu-id="6aabd-119">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6aabd-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aabd-120">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="6aabd-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6aabd-121">**ライブラリ:** Fusion .dll と Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="6aabd-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="6aabd-122">Mscorwks.dll の代わりに Fusion を使用して、正しいバージョンの .NET Framework を対象としていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6aabd-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="6aabd-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aabd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aabd-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="6aabd-124">See also</span></span>

- [<span data-ttu-id="6aabd-125">CreateHistoryReader 関数</span><span class="sxs-lookup"><span data-stu-id="6aabd-125">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="6aabd-126">NukeDownloadedCache 関数</span><span class="sxs-lookup"><span data-stu-id="6aabd-126">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)
- [<span data-ttu-id="6aabd-127">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="6aabd-127">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
