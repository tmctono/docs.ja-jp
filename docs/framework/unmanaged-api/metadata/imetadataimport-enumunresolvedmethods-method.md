---
title: IMetaDataImport::EnumUnresolvedMethods メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
ms.openlocfilehash: ff9827174e43fd62f3a995e9f477c6fff66b227a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449958"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="4d664-102">IMetaDataImport::EnumUnresolvedMethods メソッド</span><span class="sxs-lookup"><span data-stu-id="4d664-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="4d664-103">現在のメタデータ スコープ内の未解決のメソッドを表す MemberDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="4d664-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d664-104">構文</span><span class="sxs-lookup"><span data-stu-id="4d664-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d664-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4d664-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4d664-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4d664-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="4d664-107">このメソッドの最初の呼び出しでは、この値は NULL である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d664-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="4d664-108">入出力MemberDef トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="4d664-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4d664-109">[in] `rMethods` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="4d664-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="4d664-110">入出力`rMethods`で返された MemberDef トークンの数。</span><span class="sxs-lookup"><span data-stu-id="4d664-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d664-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="4d664-111">Return Value</span></span>  
  
|<span data-ttu-id="4d664-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4d664-112">HRESULT</span></span>|<span data-ttu-id="4d664-113">説明</span><span class="sxs-lookup"><span data-stu-id="4d664-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4d664-114">`EnumUnresolvedMethods` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="4d664-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4d664-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="4d664-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="4d664-116">この場合、`pcTokens` は0になります。</span><span class="sxs-lookup"><span data-stu-id="4d664-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d664-117">コメント</span><span class="sxs-lookup"><span data-stu-id="4d664-117">Remarks</span></span>  
 <span data-ttu-id="4d664-118">未解決のメソッドとは、宣言されていても実装されていないメソッドです。</span><span class="sxs-lookup"><span data-stu-id="4d664-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="4d664-119">メソッドが `miForwardRef` としてマークされ、`mdPinvokeImpl` または `miRuntime` が0に設定されている場合、メソッドは列挙体に含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d664-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="4d664-120">つまり、未解決のメソッドは `miForwardRef` としてマークされているものの、アンマネージコードでは実装されていない (PInvoke 経由で)、またはランタイム自体によって内部的に実装されていないクラスメソッドです。</span><span class="sxs-lookup"><span data-stu-id="4d664-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="4d664-121">列挙体には、モジュールスコープ (globals) またはインターフェイスまたは抽象クラスで定義されているすべてのメソッドが除外されます。</span><span class="sxs-lookup"><span data-stu-id="4d664-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d664-122">要件</span><span class="sxs-lookup"><span data-stu-id="4d664-122">Requirements</span></span>  
 <span data-ttu-id="4d664-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d664-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d664-124">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="4d664-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4d664-125">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4d664-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4d664-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d664-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d664-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d664-127">See also</span></span>

- [<span data-ttu-id="4d664-128">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d664-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4d664-129">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d664-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
