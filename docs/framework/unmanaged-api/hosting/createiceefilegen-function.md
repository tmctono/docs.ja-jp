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
ms.openlocfilehash: de27851b4afc3eccad46531848c68723bff346d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136829"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="8926f-102">CreateICeeFileGen 関数</span><span class="sxs-lookup"><span data-stu-id="8926f-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="8926f-103">[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8926f-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="8926f-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="8926f-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8926f-105">構文</span><span class="sxs-lookup"><span data-stu-id="8926f-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8926f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8926f-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="8926f-107">入出力新しい `ICeeFileGen` オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8926f-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8926f-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="8926f-108">Return Value</span></span>  
 <span data-ttu-id="8926f-109">このメソッドは、標準の COM エラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="8926f-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8926f-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="8926f-110">Remarks</span></span>  
 <span data-ttu-id="8926f-111">`ICeeFileGen` オブジェクトは、共通言語ランタイム (CLR) の移植可能な実行可能 (PE) ファイルを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8926f-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="8926f-112">[DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)関数を呼び出して、完了時に `ICeeFileGen` オブジェクトを破棄します。</span><span class="sxs-lookup"><span data-stu-id="8926f-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8926f-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="8926f-113">Requirements</span></span>  
 <span data-ttu-id="8926f-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8926f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8926f-115">**ヘッダー:** ICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="8926f-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="8926f-116">**ライブラリ:** MSCorPE</span><span class="sxs-lookup"><span data-stu-id="8926f-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="8926f-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8926f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8926f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="8926f-118">See also</span></span>

- [<span data-ttu-id="8926f-119">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="8926f-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
