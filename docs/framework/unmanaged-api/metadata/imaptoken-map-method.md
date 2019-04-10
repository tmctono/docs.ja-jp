---
title: IMapToken::Map メソッド
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a85dc586b0c08fabdd34c018e82314c9003eeded
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171015"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="b98de-102">IMapToken::Map メソッド</span><span class="sxs-lookup"><span data-stu-id="b98de-102">IMapToken::Map Method</span></span>
<span data-ttu-id="b98de-103">メタデータ署名を使用して、アセンブリ間のリレーションシップをマップします。</span><span class="sxs-lookup"><span data-stu-id="b98de-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b98de-104">構文</span><span class="sxs-lookup"><span data-stu-id="b98de-104">Syntax</span></span>  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b98de-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b98de-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="b98de-106">[in]コードをインポート オブジェクトを表すメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="b98de-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="b98de-107">[in]出力コード オブジェクトを表すメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="b98de-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b98de-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="b98de-108">Remarks</span></span>  
 <span data-ttu-id="b98de-109">トークンの再マップは、マージ中が発生、インポートされた (ソース) のメタデータ スコープ内に元のトークンがスコープ設定し、出力 (ターゲット) のメタデータ スコープに新しいトークンがスコープ設定します。</span><span class="sxs-lookup"><span data-stu-id="b98de-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b98de-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="b98de-110">Requirements</span></span>  
 <span data-ttu-id="b98de-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b98de-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b98de-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b98de-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b98de-113">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="b98de-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="b98de-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="b98de-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b98de-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b98de-115">See also</span></span>

- [<span data-ttu-id="b98de-116">IMapToken インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b98de-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
