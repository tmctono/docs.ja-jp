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
ms.openlocfilehash: 34ecfc2f01f22971e135358806adeea632e02f8b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448030"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="6a1d2-102">IMetaDataEmit::MergeEnd メソッド</span><span class="sxs-lookup"><span data-stu-id="6a1d2-102">IMetaDataEmit::MergeEnd Method</span></span>

<span data-ttu-id="6a1d2-103">[IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)の1つ以上の前の呼び出しで指定されたすべてのメタデータスコープを現在のスコープにマージします。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="6a1d2-104">構文</span><span class="sxs-lookup"><span data-stu-id="6a1d2-104">Syntax</span></span>

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a><span data-ttu-id="6a1d2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6a1d2-105">Parameters</span></span>

<span data-ttu-id="6a1d2-106">このメソッドはパラメーターを受け取りません。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-106">This method takes no parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="6a1d2-107">コメント</span><span class="sxs-lookup"><span data-stu-id="6a1d2-107">Remarks</span></span>

<span data-ttu-id="6a1d2-108">このルーチンは、前の `IMetaDataEmit::Merge`の呼び出しで指定されたすべてのインポートスコープのメタデータの実際のマージを現在の出力スコープにトリガーします。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>

<span data-ttu-id="6a1d2-109">マージには、次の特殊な条件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-109">The following special conditions apply to the merge:</span></span>

- <span data-ttu-id="6a1d2-110">モジュールバージョン識別子 (MVID) はインポートされません。これは、インポートスコープ内のメタデータに固有であるためです。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>

- <span data-ttu-id="6a1d2-111">既存のモジュール全体のプロパティは上書きされません。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-111">No existing module-wide properties are overwritten.</span></span>

  <span data-ttu-id="6a1d2-112">モジュールのプロパティが現在のスコープに対して既に設定されている場合は、モジュールのプロパティはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="6a1d2-113">ただし、モジュールのプロパティが現在のスコープで設定されていない場合は、最初に検出されたときに1回だけインポートされます。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="6a1d2-114">これらのモジュールのプロパティが再度検出された場合、それらは重複しています。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="6a1d2-115">すべてのモジュールプロパティ (MVID を除く) の値が比較され、重複が見つからない場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>

- <span data-ttu-id="6a1d2-116">型定義 (`TypeDef`) の場合、重複は現在のスコープにマージされません。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="6a1d2-117">`TypeDef` オブジェクトの + *GUID* + *バージョン番号*の各*完全修飾オブジェクト名*に対して重複がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="6a1d2-118">名前または GUID に一致するものがあり、他の2つの要素のいずれかが異なる場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="6a1d2-119">それ以外の場合、3つすべての項目が一致すると、`MergeEnd` は、エントリが実際に重複していることを確認するための大まかなチェックを行います。それ以外の場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="6a1d2-120">この大まかなチェックは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-120">This cursory check looks for:</span></span>

  - <span data-ttu-id="6a1d2-121">同じ順序で発生する同じメンバー宣言。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="6a1d2-122">`mdPrivateScope` としてフラグが設定されているメンバー (「 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)列挙体」を参照) は、このチェックには含まれていません。これらは特別にマージされます。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>

  - <span data-ttu-id="6a1d2-123">同じクラスレイアウト。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-123">The same class layout.</span></span>

  <span data-ttu-id="6a1d2-124">つまり、`TypeDef` オブジェクトは、宣言されているすべてのメタデータスコープで常に完全かつ一貫して定義される必要があります。メンバーの実装 (クラスの場合) が複数のコンパイル単位にわたって分散されている場合、完全な定義はすべてのスコープに存在すると見なされ、各スコープに増分されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="6a1d2-125">たとえば、パラメーター名がコントラクトに関連する場合は、すべてのスコープに同じ方法で出力する必要があります。これらが関連性のない場合は、メタデータに出力されません。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>

  <span data-ttu-id="6a1d2-126">例外として、`TypeDef` オブジェクトは `mdPrivateScope`としてフラグが設定された増分メンバーを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="6a1d2-127">これらの問題が発生すると、`MergeEnd` によって、重複の有無に関係なく、現在のスコープに増分的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="6a1d2-128">コンパイラはプライベートスコープを認識しているため、コンパイラは規則の適用を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>

- <span data-ttu-id="6a1d2-129">相対仮想アドレス (RVAs) はインポートまたはマージされません。コンパイラは、この情報を再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>

- <span data-ttu-id="6a1d2-130">カスタム属性は、関連付けられているアイテムがマージされた場合にのみマージされます。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="6a1d2-131">たとえば、クラスに関連付けられているカスタム属性は、クラスが最初に検出されたときにマージされます。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="6a1d2-132">カスタム属性がコンパイル単位に固有の `TypeDef` または `MemberDef` に関連付けられている場合 (メンバーコンパイルのタイムスタンプなど) は、マージされず、そのようなメタデータを削除または更新するためにコンパイラによって行われます。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="6a1d2-133">要件</span><span class="sxs-lookup"><span data-stu-id="6a1d2-133">Requirements</span></span>

<span data-ttu-id="6a1d2-134">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="6a1d2-135">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="6a1d2-135">**Header:** Cor.h</span></span>

<span data-ttu-id="6a1d2-136">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="6a1d2-136">**Library:** Used as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="6a1d2-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a1d2-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6a1d2-138">参照</span><span class="sxs-lookup"><span data-stu-id="6a1d2-138">See also</span></span>

- [<span data-ttu-id="6a1d2-139">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a1d2-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6a1d2-140">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a1d2-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
