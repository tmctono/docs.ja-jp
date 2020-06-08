---
title: IMetaDataEmit2::DefineMethodSpec メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
ms.openlocfilehash: 8e067dc4943e6847177c13a683703e3a649a49e4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503823"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="5a6dc-102">IMetaDataEmit2::DefineMethodSpec メソッド</span><span class="sxs-lookup"><span data-stu-id="5a6dc-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="5a6dc-103">メソッドのジェネリックインスタンスを作成し、その定義へのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="5a6dc-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a6dc-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a6dc-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a6dc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a6dc-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="5a6dc-106">からジェネリックインスタンスを作成するメソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="5a6dc-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="5a6dc-107">トークンは、型または型である必要があり `mdMethodDef` `mdMemberRef` ます。</span><span class="sxs-lookup"><span data-stu-id="5a6dc-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="5a6dc-108">からメソッドのバイナリ COM + シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5a6dc-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="5a6dc-109">からのサイズ (バイト単位) `pvSigBlob` 。</span><span class="sxs-lookup"><span data-stu-id="5a6dc-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="5a6dc-110">入出力メソッドのメタデータシグネチャ定義へのトークン。</span><span class="sxs-lookup"><span data-stu-id="5a6dc-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a6dc-111">要件</span><span class="sxs-lookup"><span data-stu-id="5a6dc-111">Requirements</span></span>  
 <span data-ttu-id="5a6dc-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a6dc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a6dc-113">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="5a6dc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a6dc-114">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a6dc-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a6dc-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a6dc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a6dc-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a6dc-116">See also</span></span>

- [<span data-ttu-id="5a6dc-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a6dc-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="5a6dc-118">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a6dc-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
