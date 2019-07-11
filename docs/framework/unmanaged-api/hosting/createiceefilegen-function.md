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
ms.openlocfilehash: 96968de84182b74f7baa89d5dfc12a4797ade595
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779231"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="b9512-102">CreateICeeFileGen 関数</span><span class="sxs-lookup"><span data-stu-id="b9512-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="b9512-103">作成、 [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b9512-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="b9512-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="b9512-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9512-105">構文</span><span class="sxs-lookup"><span data-stu-id="b9512-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9512-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9512-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="b9512-107">[out]新しいアドレスへのポインター`ICeeFileGen`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b9512-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9512-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="b9512-108">Return Value</span></span>  
 <span data-ttu-id="b9512-109">このメソッドは、標準の COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="b9512-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9512-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b9512-110">Remarks</span></span>  
 <span data-ttu-id="b9512-111">`ICeeFileGen`オブジェクトが共通言語ランタイム (CLR) のポータブル実行可能 (PE) ファイルを作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="b9512-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="b9512-112">呼び出す、 [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)を破棄する関数、`ICeeFileGen`オブジェクトの終了時にします。</span><span class="sxs-lookup"><span data-stu-id="b9512-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9512-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="b9512-113">Requirements</span></span>  
 <span data-ttu-id="b9512-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9512-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9512-115">**ヘッダー:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="b9512-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="b9512-116">**ライブラリ:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="b9512-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="b9512-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9512-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9512-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9512-118">See also</span></span>

- [<span data-ttu-id="b9512-119">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="b9512-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
