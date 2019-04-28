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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 566f73335861a8eb769b21a254e0e93b51a78d02
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756391"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="fa816-102">CreateICeeFileGen 関数</span><span class="sxs-lookup"><span data-stu-id="fa816-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="fa816-103">作成、 [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="fa816-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="fa816-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="fa816-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa816-105">構文</span><span class="sxs-lookup"><span data-stu-id="fa816-105">Syntax</span></span>  
  
```  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa816-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa816-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="fa816-107">[out]新しいアドレスへのポインター`ICeeFileGen`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="fa816-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa816-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="fa816-108">Return Value</span></span>  
 <span data-ttu-id="fa816-109">このメソッドは、標準の COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="fa816-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa816-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="fa816-110">Remarks</span></span>  
 <span data-ttu-id="fa816-111">`ICeeFileGen`オブジェクトが共通言語ランタイム (CLR) のポータブル実行可能 (PE) ファイルを作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="fa816-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="fa816-112">呼び出す、 [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)を破棄する関数、`ICeeFileGen`オブジェクトの終了時にします。</span><span class="sxs-lookup"><span data-stu-id="fa816-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa816-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="fa816-113">Requirements</span></span>  
 <span data-ttu-id="fa816-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa816-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa816-115">**ヘッダー:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="fa816-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="fa816-116">**ライブラリ:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="fa816-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="fa816-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa816-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa816-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa816-118">See also</span></span>

- [<span data-ttu-id="fa816-119">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="fa816-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
