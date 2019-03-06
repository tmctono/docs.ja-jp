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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 012cd9fdf23206f57662c854692ba53f403b727f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471603"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="6e427-102">IMetaDataEmit2::DefineMethodSpec メソッド</span><span class="sxs-lookup"><span data-stu-id="6e427-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="6e427-103">メソッドのジェネリック インスタンスを作成し、定義するためのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="6e427-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e427-104">構文</span><span class="sxs-lookup"><span data-stu-id="6e427-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e427-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e427-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="6e427-106">[in]ジェネリックのインスタンスを作成する対象のメソッドのトークンです。</span><span class="sxs-lookup"><span data-stu-id="6e427-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="6e427-107">トークン型でなければなりません`mdMethodDef`または`mdMemberRef`します。</span><span class="sxs-lookup"><span data-stu-id="6e427-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="6e427-108">[in]メソッドのバイナリの COM + シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6e427-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="6e427-109">[in]サイズ (バイト単位) の`pvSigBlob`します。</span><span class="sxs-lookup"><span data-stu-id="6e427-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="6e427-110">[out]メソッドのメタデータ署名定義のトークン。</span><span class="sxs-lookup"><span data-stu-id="6e427-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e427-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6e427-111">Requirements</span></span>  
 <span data-ttu-id="6e427-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e427-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e427-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6e427-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e427-114">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="6e427-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e427-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e427-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e427-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e427-116">See also</span></span>
- [<span data-ttu-id="6e427-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e427-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="6e427-118">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e427-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
