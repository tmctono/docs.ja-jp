---
title: IMetaDataEmit::MergeEnd メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.MergeEnd
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b4e3045476fc68dbeb545b7394b373be4ff881c8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64584277"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="e267f-102">IMetaDataEmit::MergeEnd メソッド</span><span class="sxs-lookup"><span data-stu-id="e267f-102">IMetaDataEmit::MergeEnd Method</span></span>
<span data-ttu-id="e267f-103">マージを現在のスコープを 1 つまたは複数の前の呼び出しで指定されたすべてのメタデータ スコープ[imetadataemit::merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="e267f-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e267f-104">構文</span><span class="sxs-lookup"><span data-stu-id="e267f-104">Syntax</span></span>  
  
```  
HRESULT MergeEnd ();  
```  
  
## <a name="parameters"></a><span data-ttu-id="e267f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e267f-105">Parameters</span></span>  
 <span data-ttu-id="e267f-106">このメソッドには、パラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="e267f-106">This method takes no parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e267f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e267f-107">Remarks</span></span>  
 <span data-ttu-id="e267f-108">このルーチンはトリガーのメタデータの実際の結合は、すべてのインポート前の呼び出しによって指定されたスコープ`IMetaDataEmit::Merge`出力の現在のスコープにします。</span><span class="sxs-lookup"><span data-stu-id="e267f-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>  
  
 <span data-ttu-id="e267f-109">マージに、次の特殊な条件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e267f-109">The following special conditions apply to the merge:</span></span>  
  
- <span data-ttu-id="e267f-110">モジュールのバージョン id (MVID) は、インポート スコープ内のメタデータに一意であるため、まったくインポートします。</span><span class="sxs-lookup"><span data-stu-id="e267f-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>  
  
- <span data-ttu-id="e267f-111">既存のモジュール全体のプロパティは上書きされません。</span><span class="sxs-lookup"><span data-stu-id="e267f-111">No existing module-wide properties are overwritten.</span></span>  
  
     <span data-ttu-id="e267f-112">モジュールのプロパティは、現在のスコープで既に設定された、モジュールのプロパティはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="e267f-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="e267f-113">ただし、現在のスコープ内でモジュールのプロパティが設定されていない、最初に検出されたときに、一度だけがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="e267f-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="e267f-114">これらのモジュールのプロパティが再度発生した場合、重複しています。</span><span class="sxs-lookup"><span data-stu-id="e267f-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="e267f-115">(MVID) を除くすべてのモジュールのプロパティの値が比較され、重複が見つからなかった場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e267f-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>  
  
- <span data-ttu-id="e267f-116">型の定義 (`TypeDef`)、現在のスコープに重複はマージされません。</span><span class="sxs-lookup"><span data-stu-id="e267f-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="e267f-117">`TypeDef` オブジェクトはそれぞれに対して重複をチェック*オブジェクトの完全修飾名* + *GUID* + *バージョン番号*します。</span><span class="sxs-lookup"><span data-stu-id="e267f-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="e267f-118">名前または GUID のいずれかで一致があるその他の 2 つの要素のいずれかが異なる場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e267f-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="e267f-119">それ以外の場合、3 つすべての項目が一致する場合`MergeEnd`エントリが重複しないことを確認する簡単なチェックがない場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e267f-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="e267f-120">この簡単なチェックを探します。</span><span class="sxs-lookup"><span data-stu-id="e267f-120">This cursory check looks for:</span></span>  
  
    - <span data-ttu-id="e267f-121">同じメンバー宣言を同じ順序で発生しています。</span><span class="sxs-lookup"><span data-stu-id="e267f-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="e267f-122">メンバーとしてフラグが付いている`mdPrivateScope`(を参照してください、 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)列挙型)。 この確認には含まれません特別にマージされます。</span><span class="sxs-lookup"><span data-stu-id="e267f-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>  
  
    - <span data-ttu-id="e267f-123">同じクラス レイアウト。</span><span class="sxs-lookup"><span data-stu-id="e267f-123">The same class layout.</span></span>  
  
     <span data-ttu-id="e267f-124">つまり、`TypeDef`オブジェクトする必要があります常に完全かつ一貫して定義するすべてのメタデータ スコープで宣言されている完全な定義があると見なされます (クラス) をそのメンバーの実装が複数のコンパイル単位に分散している場合。すべてのスコープに存在して各スコープには増分されません。</span><span class="sxs-lookup"><span data-stu-id="e267f-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="e267f-125">たとえば、パラメーター名、コントラクトに関連する場合が送出同様に、すべてのスコープに関連いない場合、それらがメタデータに出力しないする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e267f-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>  
  
     <span data-ttu-id="e267f-126">例外が、`TypeDef`オブジェクトとしてフラグが設定された増分のメンバーを持つことが`mdPrivateScope`します。</span><span class="sxs-lookup"><span data-stu-id="e267f-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="e267f-127">これらは、発生時に`MergeEnd`増分重複に関係なく、現在のスコープに追加します。</span><span class="sxs-lookup"><span data-stu-id="e267f-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="e267f-128">コンパイラは、プライベート スコープを認識するため、コンパイラはルールの適用を担当である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e267f-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>  
  
- <span data-ttu-id="e267f-129">相対仮想アドレス (Rva) がインポートまたは; マージできません。コンパイラは、この情報を再生成が必要です。</span><span class="sxs-lookup"><span data-stu-id="e267f-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>  
  
- <span data-ttu-id="e267f-130">アタッチされている項目がマージされた場合にのみ、カスタム属性がマージされます。</span><span class="sxs-lookup"><span data-stu-id="e267f-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="e267f-131">たとえば、クラスに関連付けられているカスタム属性は、クラスが最初に検出されたときにマージされます。</span><span class="sxs-lookup"><span data-stu-id="e267f-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="e267f-132">カスタム属性が関連付けられている場合、`TypeDef`または`MemberDef`はマージされません、削除またはそのようなメタデータを更新するコンパイラの責任です (メンバーのコンパイルのタイムスタンプ) などのコンパイル単位に固有です。</span><span class="sxs-lookup"><span data-stu-id="e267f-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e267f-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="e267f-133">Requirements</span></span>  
 <span data-ttu-id="e267f-134">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e267f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e267f-135">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e267f-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e267f-136">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="e267f-136">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e267f-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e267f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e267f-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="e267f-138">See also</span></span>

- [<span data-ttu-id="e267f-139">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e267f-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e267f-140">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e267f-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
