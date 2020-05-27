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
ms.openlocfilehash: 832adacac4a6df9ccf21578538a1c557150f3ba1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008782"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="fa28b-102">IMetaDataDispenserEx::GetOption メソッド</span><span class="sxs-lookup"><span data-stu-id="fa28b-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="fa28b-103">現在のメタデータスコープの指定したオプションの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa28b-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="fa28b-104">オプションは、現在のメタデータスコープへの呼び出しの処理方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="fa28b-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa28b-105">構文</span><span class="sxs-lookup"><span data-stu-id="fa28b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa28b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa28b-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="fa28b-107">から取得するオプションを指定する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fa28b-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="fa28b-108">サポートされている Guid の一覧については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa28b-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="fa28b-109">入出力返されたオプションの値。</span><span class="sxs-lookup"><span data-stu-id="fa28b-109">[out] The value of the returned option.</span></span> <span data-ttu-id="fa28b-110">この値の型は、指定されたオプションの型のバリアントになります。</span><span class="sxs-lookup"><span data-stu-id="fa28b-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa28b-111">コメント</span><span class="sxs-lookup"><span data-stu-id="fa28b-111">Remarks</span></span>  
 <span data-ttu-id="fa28b-112">次の一覧は、このメソッドでサポートされている Guid を示しています。</span><span class="sxs-lookup"><span data-stu-id="fa28b-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="fa28b-113">説明については、 [IMetaDataDispenserEx:: SetOption](imetadatadispenserex-setoption-method.md)メソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa28b-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="fa28b-114">`optionId`がこのリストに含まれていない場合、このメソッドは HRESULT を返し `E_INVALIDARG` ます。パラメーターが正しくないことを示します。</span><span class="sxs-lookup"><span data-stu-id="fa28b-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="fa28b-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="fa28b-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="fa28b-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="fa28b-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="fa28b-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="fa28b-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="fa28b-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="fa28b-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="fa28b-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="fa28b-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="fa28b-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="fa28b-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="fa28b-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="fa28b-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa28b-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="fa28b-122">Requirements</span></span>  
 <span data-ttu-id="fa28b-123">**プラットフォーム:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa28b-123">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa28b-124">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="fa28b-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa28b-125">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="fa28b-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fa28b-126">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa28b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa28b-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa28b-127">See also</span></span>

- [<span data-ttu-id="fa28b-128">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa28b-128">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="fa28b-129">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa28b-129">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
