---
title: ICorDebugProcess6::GetExportStepInfo メソッド
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18af0dde2d1acc65003558a04789de027bb9209f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967407"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="f1c12-102">ICorDebugProcess6::GetExportStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="f1c12-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="f1c12-103">マネージド コードのステップ実行に役立つランタイム エクスポート関数の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f1c12-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1c12-104">構文</span><span class="sxs-lookup"><span data-stu-id="f1c12-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1c12-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1c12-105">Parameters</span></span>  
 <span data-ttu-id="f1c12-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="f1c12-106">pszExportName</span></span>  
 <span data-ttu-id="f1c12-107">[入力] PE エクスポート テーブルに書き込まれるランタイム エクスポート関数の名前。</span><span class="sxs-lookup"><span data-stu-id="f1c12-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="f1c12-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="f1c12-108">invokeKind</span></span>  
 <span data-ttu-id="f1c12-109">入出力エクスポートされた関数がマネージコードを呼び出す方法を記述する[Cordebugcodeinvokekind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)列挙体のメンバーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f1c12-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="f1c12-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="f1c12-110">invokePurpose</span></span>  
 <span data-ttu-id="f1c12-111">入出力エクスポートされた関数がマネージコードを呼び出す理由を示す[Cordebugcodeinvokepurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)の列挙体のメンバーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f1c12-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1c12-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="f1c12-112">Return Value</span></span>  
 <span data-ttu-id="f1c12-113">メソッドは、次の表に記載されている値を返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1c12-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="f1c12-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="f1c12-114">Return value</span></span>|<span data-ttu-id="f1c12-115">説明</span><span class="sxs-lookup"><span data-stu-id="f1c12-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="f1c12-116">メソッド呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="f1c12-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="f1c12-117">`pInvokeKind`また`pInvokePurpose`はが**null**です。</span><span class="sxs-lookup"><span data-stu-id="f1c12-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="f1c12-118">その他の失敗した `HRESULT` 値。</span><span class="sxs-lookup"><span data-stu-id="f1c12-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="f1c12-119">必要に応じて。</span><span class="sxs-lookup"><span data-stu-id="f1c12-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1c12-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1c12-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1c12-121">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1c12-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1c12-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="f1c12-122">Requirements</span></span>  
 <span data-ttu-id="f1c12-123">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1c12-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1c12-124">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f1c12-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1c12-125">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="f1c12-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1c12-126">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1c12-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c12-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1c12-127">See also</span></span>

- [<span data-ttu-id="f1c12-128">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1c12-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="f1c12-129">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1c12-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
