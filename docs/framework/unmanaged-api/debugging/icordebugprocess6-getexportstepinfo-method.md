---
title: ICorDebugProcess6::GetExportStepInfo メソッド
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad094cdcc632abecf3b19cbcbfce24220fedcaf5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736403"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="8b653-102">ICorDebugProcess6::GetExportStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="8b653-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="8b653-103">マネージド コードのステップ実行に役立つランタイム エクスポート関数の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8b653-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b653-104">構文</span><span class="sxs-lookup"><span data-stu-id="8b653-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b653-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8b653-105">Parameters</span></span>  
 <span data-ttu-id="8b653-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="8b653-106">pszExportName</span></span>  
 <span data-ttu-id="8b653-107">[入力] PE エクスポート テーブルに書き込まれるランタイム エクスポート関数の名前。</span><span class="sxs-lookup"><span data-stu-id="8b653-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="8b653-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="8b653-108">invokeKind</span></span>  
 <span data-ttu-id="8b653-109">[out]メンバーへのポインター、 [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)エクスポートされた関数がマネージ コードを呼び出す方法について説明する列挙体。</span><span class="sxs-lookup"><span data-stu-id="8b653-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="8b653-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="8b653-110">invokePurpose</span></span>  
 <span data-ttu-id="8b653-111">[out]メンバーへのポインター、 [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)エクスポートされた関数がマネージ コードを呼び出す理由を示す列挙体。</span><span class="sxs-lookup"><span data-stu-id="8b653-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b653-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="8b653-112">Return Value</span></span>  
 <span data-ttu-id="8b653-113">メソッドは、次の表に記載されている値を返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="8b653-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="8b653-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="8b653-114">Return value</span></span>|<span data-ttu-id="8b653-115">説明</span><span class="sxs-lookup"><span data-stu-id="8b653-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="8b653-116">メソッド呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="8b653-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="8b653-117">`pInvokeKind` または`pInvokePurpose`は**null**します。</span><span class="sxs-lookup"><span data-stu-id="8b653-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="8b653-118">その他の失敗した `HRESULT` 値。</span><span class="sxs-lookup"><span data-stu-id="8b653-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="8b653-119">必要に応じて。</span><span class="sxs-lookup"><span data-stu-id="8b653-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b653-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="8b653-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b653-121">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8b653-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b653-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="8b653-122">Requirements</span></span>  
 <span data-ttu-id="8b653-123">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b653-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b653-124">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b653-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b653-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b653-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b653-126">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b653-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b653-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b653-127">See also</span></span>

- [<span data-ttu-id="8b653-128">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b653-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="8b653-129">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b653-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
