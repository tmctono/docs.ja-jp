---
title: IMetaDataDispenserEx::GetOption メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
ms.openlocfilehash: 816e2f2dc7d4d00f74f67720ee45d7b3483e57fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177726"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="88245-102">IMetaDataDispenserEx::GetOption メソッド</span><span class="sxs-lookup"><span data-stu-id="88245-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="88245-103">現在のメタデータ スコープの指定されたオプションの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="88245-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="88245-104">このオプションは、現在のメタデータ スコープへの呼び出しの処理方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="88245-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88245-105">構文</span><span class="sxs-lookup"><span data-stu-id="88245-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88245-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="88245-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="88245-107">[in]取得するオプションを指定する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="88245-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="88245-108">サポートされている GUID の一覧については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88245-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="88245-109">[アウト]返されるオプションの値。</span><span class="sxs-lookup"><span data-stu-id="88245-109">[out] The value of the returned option.</span></span> <span data-ttu-id="88245-110">この値の型は、指定されたオプションの型のバリアントになります。</span><span class="sxs-lookup"><span data-stu-id="88245-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88245-111">解説</span><span class="sxs-lookup"><span data-stu-id="88245-111">Remarks</span></span>  
 <span data-ttu-id="88245-112">このメソッドでサポートされている GUID を次に示します。</span><span class="sxs-lookup"><span data-stu-id="88245-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="88245-113">詳細については[、メソッドを](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="88245-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="88245-114">この`optionId`リストに含まれていない場合、このメソッドは、誤`E_INVALIDARG`ったパラメーターを示す HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="88245-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="88245-115">メタデータチェック重複</span><span class="sxs-lookup"><span data-stu-id="88245-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="88245-116">をチェックします。</span><span class="sxs-lookup"><span data-stu-id="88245-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="88245-117">トークンの動き</span><span class="sxs-lookup"><span data-stu-id="88245-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="88245-118">メタデータセットエンク</span><span class="sxs-lookup"><span data-stu-id="88245-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="88245-119">注文のエラーをエラーします。</span><span class="sxs-lookup"><span data-stu-id="88245-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="88245-120">メタデータ生成TCEアダプター</span><span class="sxs-lookup"><span data-stu-id="88245-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="88245-121">メタデータリンカーのオプション</span><span class="sxs-lookup"><span data-stu-id="88245-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88245-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="88245-122">Requirements</span></span>  
 <span data-ttu-id="88245-123">**プラットフォーム:**[「システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88245-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88245-124">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="88245-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="88245-125">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="88245-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="88245-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88245-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88245-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="88245-127">See also</span></span>

- [<span data-ttu-id="88245-128">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="88245-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="88245-129">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="88245-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
