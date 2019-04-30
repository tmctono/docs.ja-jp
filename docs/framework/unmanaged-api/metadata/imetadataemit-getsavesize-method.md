---
title: IMetaDataEmit::GetSaveSize メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9279808e4ad15b693d06ac8a99dd33a609e5a8f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992512"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="0ee5a-102">IMetaDataEmit::GetSaveSize メソッド</span><span class="sxs-lookup"><span data-stu-id="0ee5a-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="0ee5a-103">現在のスコープ内のアセンブリとそのメタデータの推定のバイナリのサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ee5a-104">構文</span><span class="sxs-lookup"><span data-stu-id="0ee5a-104">Syntax</span></span>  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ee5a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0ee5a-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="0ee5a-106">[in]値、 [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md)正確でないかおおよそのサイズを取得するかどうかを指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="0ee5a-107">のみの 3 つの値が無効です: cssAccurate、cssQuick、および cssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="0ee5a-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
- <span data-ttu-id="0ee5a-108">cssAccurate は正確なサイズの保存を返しますが、計算に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
- <span data-ttu-id="0ee5a-109">cssQuick は安全性、用に埋め込まれて、サイズを返しますが、計算時間がかかりません。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
- <span data-ttu-id="0ee5a-110">cssDiscardTransientCAs 指示`GetSaveSize`こと、破棄できる破棄できるカスタム属性。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="0ee5a-111">[out]ファイルを保存するために必要なサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ee5a-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="0ee5a-112">Remarks</span></span>  
 <span data-ttu-id="0ee5a-113">`GetSaveSize` 必要に応じて、(バイト単位) を現在のスコープ内でアセンブリとそのすべてのメタデータを保存する領域が計算されます。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="0ee5a-114">(への呼び出し、 [imetadataemit::savetostream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)メソッドの出力をこのバイト数)。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="0ee5a-115">呼び出し元が実装されている場合、 [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)インターフェイス (を通じて[imetadataemit::sethandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)または[imetadataemit::merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md))、`GetSaveSize`は 2 つのパスを実行最適化し、圧縮するメタデータ。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="0ee5a-116">それ以外の場合、最適化は実行されません。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="0ee5a-117">最適化を実行すると、最初のパスは単に検索のインポート時のパフォーマンスをチューニングするメタデータ構造体を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="0ee5a-118">この手順は、今後の参照用のツールによって保持されるトークンは無効になります影響で、レコードが移動は通常なります。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="0ee5a-119">メタデータはできません、呼び出し元に通知までこれらのトークンの変更の 2 番目のパスの後ただし。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="0ee5a-120">2 番目のパスのさまざまな最適化は、メタデータ、退席中 (事前バインディング) の最適化などの全体的なサイズを小さくことを意図したことがあります`mdTypeRef`と`mdMemberRef`トークンの参照が、型またはメンバーで宣言されているときに、現在のメタデータ スコープ。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="0ee5a-121">このパスでは、別の一連のトークンのマッピングが発生します。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="0ee5a-122">メタデータ エンジンは、このパスの後、を通じて、呼び出し元を通知しますその`IMapToken`のいずれかのインターフェイスは、トークンの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ee5a-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="0ee5a-123">Requirements</span></span>  
 <span data-ttu-id="0ee5a-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ee5a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ee5a-125">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0ee5a-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ee5a-126">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="0ee5a-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ee5a-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ee5a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee5a-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ee5a-128">See also</span></span>

- [<span data-ttu-id="0ee5a-129">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ee5a-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0ee5a-130">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ee5a-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
