---
title: ICorDebugProcess6::GetExportStepInfo メソッド
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: 118f52db63464b4c9355ba9ee7f330b996c5bf71
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792244"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="75f5d-102">ICorDebugProcess6::GetExportStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="75f5d-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="75f5d-103">マネージド コードのステップ実行に役立つランタイム エクスポート関数の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="75f5d-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75f5d-104">構文</span><span class="sxs-lookup"><span data-stu-id="75f5d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75f5d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="75f5d-105">Parameters</span></span>  
 <span data-ttu-id="75f5d-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="75f5d-106">pszExportName</span></span>  
 <span data-ttu-id="75f5d-107">[入力] PE エクスポート テーブルに書き込まれるランタイム エクスポート関数の名前。</span><span class="sxs-lookup"><span data-stu-id="75f5d-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="75f5d-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="75f5d-108">invokeKind</span></span>  
 <span data-ttu-id="75f5d-109">入出力エクスポートされた関数がマネージコードを呼び出す方法を記述する[Cordebugcodeinvokekind](cordebugcodeinvokekind-enumeration.md)列挙体のメンバーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="75f5d-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="75f5d-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="75f5d-110">invokePurpose</span></span>  
 <span data-ttu-id="75f5d-111">入出力エクスポートされた関数がマネージコードを呼び出す理由を示す[Cordebugcodeinvokepurpose](cordebugcodeinvokepurpose-enumeration.md)の列挙体のメンバーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="75f5d-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75f5d-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="75f5d-112">Return Value</span></span>  
 <span data-ttu-id="75f5d-113">メソッドは、次の表に記載されている値を返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="75f5d-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="75f5d-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="75f5d-114">Return value</span></span>|<span data-ttu-id="75f5d-115">説明</span><span class="sxs-lookup"><span data-stu-id="75f5d-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="75f5d-116">メソッド呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="75f5d-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="75f5d-117">`pInvokeKind` または `pInvokePurpose` が**null**です。</span><span class="sxs-lookup"><span data-stu-id="75f5d-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="75f5d-118">その他の失敗した `HRESULT` 値。</span><span class="sxs-lookup"><span data-stu-id="75f5d-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="75f5d-119">必要に応じて。</span><span class="sxs-lookup"><span data-stu-id="75f5d-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75f5d-120">コメント</span><span class="sxs-lookup"><span data-stu-id="75f5d-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75f5d-121">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="75f5d-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75f5d-122">要件</span><span class="sxs-lookup"><span data-stu-id="75f5d-122">Requirements</span></span>  
 <span data-ttu-id="75f5d-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75f5d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75f5d-124">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75f5d-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75f5d-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75f5d-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75f5d-126">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75f5d-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f5d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="75f5d-127">See also</span></span>

- [<span data-ttu-id="75f5d-128">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75f5d-128">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="75f5d-129">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75f5d-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
