---
title: CreateICeeFileGen 関数
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: 294b82efd66704014aab1b73171afe9165f17664
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616451"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="e00ee-102">CreateICeeFileGen 関数</span><span class="sxs-lookup"><span data-stu-id="e00ee-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="e00ee-103">[ICeeFileGen](iceefilegen-class.md)オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e00ee-103">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="e00ee-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="e00ee-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e00ee-105">構文</span><span class="sxs-lookup"><span data-stu-id="e00ee-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e00ee-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e00ee-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="e00ee-107">入出力新しいオブジェクトのアドレスへのポインター `ICeeFileGen` 。</span><span class="sxs-lookup"><span data-stu-id="e00ee-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e00ee-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="e00ee-108">Return Value</span></span>  
 <span data-ttu-id="e00ee-109">このメソッドは、標準の COM エラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="e00ee-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e00ee-110">解説</span><span class="sxs-lookup"><span data-stu-id="e00ee-110">Remarks</span></span>  
 <span data-ttu-id="e00ee-111">`ICeeFileGen`オブジェクトは、共通言語ランタイム (CLR) の移植可能な実行可能 (PE) ファイルを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e00ee-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="e00ee-112">完了したら、 [DestroyICeeFileGen](destroyiceefilegen-function.md)関数を呼び出してオブジェクトを破棄し `ICeeFileGen` ます。</span><span class="sxs-lookup"><span data-stu-id="e00ee-112">Call the [DestroyICeeFileGen](destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e00ee-113">要件</span><span class="sxs-lookup"><span data-stu-id="e00ee-113">Requirements</span></span>  
 <span data-ttu-id="e00ee-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e00ee-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e00ee-115">**ヘッダー:** ICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="e00ee-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="e00ee-116">**ライブラリ:** MSCorPE</span><span class="sxs-lookup"><span data-stu-id="e00ee-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="e00ee-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e00ee-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e00ee-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e00ee-118">See also</span></span>

- [<span data-ttu-id="e00ee-119">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="e00ee-119">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
