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
ms.openlocfilehash: f323e91e60c9735a51e955eaab6673ca167f294d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951879"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="6b4a5-102">IMetaDataImport::ResolveTypeRef メソッド</span><span class="sxs-lookup"><span data-stu-id="6b4a5-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="6b4a5-103">指定し<xref:System.Type>た TypeRef トークンによって表される参照を解決します。</span><span class="sxs-lookup"><span data-stu-id="6b4a5-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b4a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="6b4a5-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b4a5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b4a5-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="6b4a5-106">から参照される型情報を返す TypeRef メタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="6b4a5-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="6b4a5-107">から返されるインターフェイスの IID `ppIScope`。</span><span class="sxs-lookup"><span data-stu-id="6b4a5-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="6b4a5-108">通常、これは IID_IMetaDataImport です。</span><span class="sxs-lookup"><span data-stu-id="6b4a5-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="6b4a5-109">入出力参照される型が定義されているモジュールスコープへのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6b4a5-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="6b4a5-110">入出力参照された型を表す TypeDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6b4a5-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b4a5-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="6b4a5-111">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6b4a5-112">複数のアプリケーションドメインが読み込まれる場合は、この方法を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6b4a5-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="6b4a5-113">メソッドは、アプリケーションドメインの境界を尊重しません。</span><span class="sxs-lookup"><span data-stu-id="6b4a5-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="6b4a5-114">アセンブリの複数のバージョンが読み込まれ、同じ名前空間を持つ同じ型が含まれている場合、メソッドは最初に見つかった型のモジュールスコープを返します。</span><span class="sxs-lookup"><span data-stu-id="6b4a5-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="6b4a5-115">メソッド`ResolveTypeRef`は、他のモジュールで型定義を検索します。</span><span class="sxs-lookup"><span data-stu-id="6b4a5-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="6b4a5-116">型定義が見つかった場合は`ResolveTypeRef` 、そのモジュールスコープへのインターフェイスと、その型の TypeDef トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="6b4a5-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="6b4a5-117">解決する型参照の解決スコープが AssemblyRef である場合、メソッドは`ResolveTypeRef` 、 [IMetaDataDispenser:: openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)メソッドまたは[を呼び出して既に開かれているメタデータスコープ内でのみ一致を検索します。IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="6b4a5-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="6b4a5-118">これは、 `ResolveTypeRef`が、ディスク上またはグローバルアセンブリキャッシュ内の、アセンブリが格納されている AssemblyRef スコープからしか判断できないためです。</span><span class="sxs-lookup"><span data-stu-id="6b4a5-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b4a5-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="6b4a5-119">Requirements</span></span>  
 <span data-ttu-id="6b4a5-120">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b4a5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b4a5-121">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="6b4a5-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b4a5-122">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6b4a5-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6b4a5-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b4a5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b4a5-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b4a5-124">See also</span></span>

- [<span data-ttu-id="6b4a5-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b4a5-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6b4a5-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b4a5-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
