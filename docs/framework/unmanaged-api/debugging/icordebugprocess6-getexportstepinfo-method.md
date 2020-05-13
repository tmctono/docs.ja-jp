---
title: ICorDebugProcess6::GetExportStepInfo メソッド
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: 9d195c61d95f084c7b6b40d2c81623fd81cd94cf
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206351"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="6813c-102">ICorDebugProcess6::GetExportStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="6813c-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="6813c-103">マネージド コードのステップ実行に役立つランタイム エクスポート関数の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6813c-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6813c-104">構文</span><span class="sxs-lookup"><span data-stu-id="6813c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,
    [out] CorDebugCodeInvokeKind* pInvokeKind,
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6813c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6813c-105">Parameters</span></span>  
 <span data-ttu-id="6813c-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="6813c-106">pszExportName</span></span>  
 <span data-ttu-id="6813c-107">[入力] PE エクスポート テーブルに書き込まれるランタイム エクスポート関数の名前。</span><span class="sxs-lookup"><span data-stu-id="6813c-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="6813c-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="6813c-108">invokeKind</span></span>  
 <span data-ttu-id="6813c-109">入出力エクスポートされた関数がマネージコードを呼び出す方法を記述する[Cordebugcodeinvokekind](cordebugcodeinvokekind-enumeration.md)列挙体のメンバーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6813c-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="6813c-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="6813c-110">invokePurpose</span></span>  
 <span data-ttu-id="6813c-111">入出力エクスポートされた関数がマネージコードを呼び出す理由を示す[Cordebugcodeinvokepurpose](cordebugcodeinvokepurpose-enumeration.md)の列挙体のメンバーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6813c-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6813c-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="6813c-112">Return Value</span></span>  
 <span data-ttu-id="6813c-113">メソッドは、次の表に記載されている値を返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="6813c-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="6813c-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="6813c-114">Return value</span></span>|<span data-ttu-id="6813c-115">説明</span><span class="sxs-lookup"><span data-stu-id="6813c-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="6813c-116">メソッド呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="6813c-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="6813c-117">`pInvokeKind`または `pInvokePurpose` が**null**です。</span><span class="sxs-lookup"><span data-stu-id="6813c-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="6813c-118">その他の失敗した `HRESULT` 値。</span><span class="sxs-lookup"><span data-stu-id="6813c-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="6813c-119">必要に応じて。</span><span class="sxs-lookup"><span data-stu-id="6813c-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6813c-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="6813c-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6813c-121">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6813c-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6813c-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="6813c-122">Requirements</span></span>  
 <span data-ttu-id="6813c-123">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6813c-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6813c-124">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6813c-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6813c-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6813c-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6813c-126">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6813c-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6813c-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="6813c-127">See also</span></span>

- [<span data-ttu-id="6813c-128">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6813c-128">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="6813c-129">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="6813c-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
