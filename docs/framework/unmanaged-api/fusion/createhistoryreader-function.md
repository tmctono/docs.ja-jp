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
ms.openlocfilehash: 80979f0424469bb1d4771ad6507bb8c9d5364ab4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108605"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="38c77-102">CreateHistoryReader 関数</span><span class="sxs-lookup"><span data-stu-id="38c77-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="38c77-103">指定されたファイルの履歴リーダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="38c77-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38c77-104">構文</span><span class="sxs-lookup"><span data-stu-id="38c77-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="38c77-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="38c77-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="38c77-106">からファイルパス。</span><span class="sxs-lookup"><span data-stu-id="38c77-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="38c77-107">入出力正常に完了した場合は、履歴リーダーへのポインターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="38c77-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38c77-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="38c77-108">Return Value</span></span>  
 <span data-ttu-id="38c77-109">このメソッドは、次の表で説明する値に加えて、Winerror.h で定義されている標準 COM エラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="38c77-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="38c77-110">リターン コード</span><span class="sxs-lookup"><span data-stu-id="38c77-110">Return code</span></span>|<span data-ttu-id="38c77-111">説明</span><span class="sxs-lookup"><span data-stu-id="38c77-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="38c77-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="38c77-112">S_OK</span></span>|<span data-ttu-id="38c77-113">メソッドが正常に完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="38c77-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="38c77-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="38c77-114">E_INVALIDARG</span></span>|<span data-ttu-id="38c77-115">`wzFilePath` または `ppHistoryReader` が null 参照に設定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="38c77-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38c77-116">［要件］</span><span class="sxs-lookup"><span data-stu-id="38c77-116">Requirements</span></span>  
 <span data-ttu-id="38c77-117">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38c77-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38c77-118">**ライブラリ:** Fusion .dll</span><span class="sxs-lookup"><span data-stu-id="38c77-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="38c77-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38c77-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38c77-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="38c77-120">See also</span></span>

- [<span data-ttu-id="38c77-121">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="38c77-121">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
