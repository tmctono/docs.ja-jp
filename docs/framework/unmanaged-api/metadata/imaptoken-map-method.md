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
ms.openlocfilehash: 428b022ed560648f59798154d5987d382938c280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176072"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="f8665-102">IMapToken::Map メソッド</span><span class="sxs-lookup"><span data-stu-id="f8665-102">IMapToken::Map Method</span></span>
<span data-ttu-id="f8665-103">メタデータ シグネチャを使用してアセンブリ間のリレーションシップをマップします。</span><span class="sxs-lookup"><span data-stu-id="f8665-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8665-104">構文</span><span class="sxs-lookup"><span data-stu-id="f8665-104">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8665-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f8665-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="f8665-106">[in]インポートされたコード オブジェクトを表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="f8665-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="f8665-107">[in]出力されたコード オブジェクトを表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="f8665-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8665-108">解説</span><span class="sxs-lookup"><span data-stu-id="f8665-108">Remarks</span></span>  
 <span data-ttu-id="f8665-109">マージ中にトークンの再マップが発生すると、元のトークンはインポートされた (ソース) メタデータ スコープでスコープが設定され、新しいトークンは出力される (ターゲット) メタデータ スコープ内でスコープが設定されます。</span><span class="sxs-lookup"><span data-stu-id="f8665-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8665-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f8665-110">Requirements</span></span>  
 <span data-ttu-id="f8665-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8665-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8665-112">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="f8665-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8665-113">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="f8665-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f8665-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8665-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8665-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8665-115">See also</span></span>

- [<span data-ttu-id="f8665-116">IMapToken インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f8665-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
