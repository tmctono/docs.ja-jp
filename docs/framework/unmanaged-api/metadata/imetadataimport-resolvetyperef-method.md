---
title: IMetaDataImport::ResolveTypeRef メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f929e6b338d4fd48b2a6ef9588523377e0dd8faa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777404"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="7aad3-102">IMetaDataImport::ResolveTypeRef メソッド</span><span class="sxs-lookup"><span data-stu-id="7aad3-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="7aad3-103">解決、<xref:System.Type>の参照を指定した TypeRef トークンによって表されます。</span><span class="sxs-lookup"><span data-stu-id="7aad3-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aad3-104">構文</span><span class="sxs-lookup"><span data-stu-id="7aad3-104">Syntax</span></span>  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7aad3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7aad3-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="7aad3-106">[in]参照先の型情報を返す TypeRef メタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="7aad3-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="7aad3-107">[in]返すインターフェイスの IID`ppIScope`します。</span><span class="sxs-lookup"><span data-stu-id="7aad3-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="7aad3-108">通常、IID_IMetaDataImport になります。</span><span class="sxs-lookup"><span data-stu-id="7aad3-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="7aad3-109">[out]参照先の型が定義されているモジュールのスコープへのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7aad3-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="7aad3-110">[out]参照先の型を表す TypeDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7aad3-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7aad3-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="7aad3-111">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7aad3-112">複数のアプリケーション ドメインが読み込まれている場合は、このメソッドを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="7aad3-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="7aad3-113">メソッドは、アプリケーション ドメインの境界を優先しません。</span><span class="sxs-lookup"><span data-stu-id="7aad3-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="7aad3-114">複数のバージョンのアセンブリが読み込まれると、同じ名前空間を持つ同じ型が含まれている場合は、最初に見つけた型のモジュールのスコープを返します。</span><span class="sxs-lookup"><span data-stu-id="7aad3-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="7aad3-115">`ResolveTypeRef`メソッドの他のモジュールの種類の定義を検索します。</span><span class="sxs-lookup"><span data-stu-id="7aad3-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="7aad3-116">型定義が見つかった場合`ResolveTypeRef`型の TypeDef トークンとそのモジュールのスコープのインターフェイスを返します。</span><span class="sxs-lookup"><span data-stu-id="7aad3-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="7aad3-117">型参照を解決する AssemblyRef の解決スコープがある場合、`ResolveTypeRef`メソッドのいずれかへの呼び出しで既に開かれているメタデータのスコープでのみ一致を検索、 [imetadatadispenser::openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)メソッドまたは[imetadatadispenser::openscopeonmemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="7aad3-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="7aad3-118">これは、ため`ResolveTypeRef`AssemblyRef スコープのみがディスク上またはグローバル アセンブリ キャッシュにアセンブリが格納される場所を判別することはできません。</span><span class="sxs-lookup"><span data-stu-id="7aad3-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aad3-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="7aad3-119">Requirements</span></span>  
 <span data-ttu-id="7aad3-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7aad3-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aad3-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7aad3-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7aad3-122">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="7aad3-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7aad3-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7aad3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aad3-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="7aad3-124">See also</span></span>

- [<span data-ttu-id="7aad3-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7aad3-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7aad3-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7aad3-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
