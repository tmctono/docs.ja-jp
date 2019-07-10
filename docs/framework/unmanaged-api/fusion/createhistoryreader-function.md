---
title: CreateHistoryReader 関数
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee30d4f32e05fab27ae70052b28d3d152594cf90
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778417"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="4ba51-102">CreateHistoryReader 関数</span><span class="sxs-lookup"><span data-stu-id="4ba51-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="4ba51-103">指定したファイルの履歴のリーダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4ba51-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ba51-104">構文</span><span class="sxs-lookup"><span data-stu-id="4ba51-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ba51-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4ba51-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="4ba51-106">[in]ファイル パス。</span><span class="sxs-lookup"><span data-stu-id="4ba51-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="4ba51-107">[out]正常に完了には、履歴リーダーへのポインターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ba51-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ba51-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="4ba51-108">Return Value</span></span>  
 <span data-ttu-id="4ba51-109">このメソッドは、次の表で説明されている値だけでなく、WinError.h で定義されている標準の COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="4ba51-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="4ba51-110">リターン コード</span><span class="sxs-lookup"><span data-stu-id="4ba51-110">Return code</span></span>|<span data-ttu-id="4ba51-111">説明</span><span class="sxs-lookup"><span data-stu-id="4ba51-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="4ba51-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ba51-112">S_OK</span></span>|<span data-ttu-id="4ba51-113">メソッドが正常に完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="4ba51-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="4ba51-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4ba51-114">E_INVALIDARG</span></span>|<span data-ttu-id="4ba51-115">示します`wzFilePath`または`ppHistoryReader`の参照を null に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4ba51-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4ba51-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="4ba51-116">Requirements</span></span>  
 <span data-ttu-id="4ba51-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ba51-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ba51-118">**ライブラリ:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="4ba51-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="4ba51-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ba51-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ba51-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ba51-120">See also</span></span>

- [<span data-ttu-id="4ba51-121">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="4ba51-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
