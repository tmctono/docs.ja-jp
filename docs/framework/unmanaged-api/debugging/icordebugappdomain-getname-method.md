---
title: ICorDebugAppDomain::GetName メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
ms.openlocfilehash: 45d27fca888bdabedf197525c63dbd03af7ba1ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179090"
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="105eb-102">ICorDebugAppDomain::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="105eb-102">ICorDebugAppDomain::GetName Method</span></span>
<span data-ttu-id="105eb-103">アプリケーション ドメインの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="105eb-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="105eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="105eb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="105eb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="105eb-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="105eb-106">[in] `szName` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="105eb-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="105eb-107">このメソッドをクエリ モードにするには、この値を 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="105eb-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="105eb-108">[アウト]名前のサイズ、または 実際に返される文字数へのポインター `szName`。</span><span class="sxs-lookup"><span data-stu-id="105eb-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="105eb-109">クエリ モードでは、この値を使用すると、呼び出し元は名前に割り当てるバッファの大きさを知ることができます。</span><span class="sxs-lookup"><span data-stu-id="105eb-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="105eb-110">[アウト]アプリケーション ドメインの名前を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="105eb-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="105eb-111">解説</span><span class="sxs-lookup"><span data-stu-id="105eb-111">Remarks</span></span>  
 <span data-ttu-id="105eb-112">デバッガーは、名前`GetName`に必要なバッファーのサイズを取得するメソッドを 1 回呼び出します。</span><span class="sxs-lookup"><span data-stu-id="105eb-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="105eb-113">デバッガーは、バッファーを割り当てるし、バッファーを埋めるために、メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="105eb-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="105eb-114">名前のサイズを取得する最初の呼び出しは、クエリ*モード*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="105eb-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="105eb-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="105eb-115">Requirements</span></span>  
 <span data-ttu-id="105eb-116">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="105eb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="105eb-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="105eb-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="105eb-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="105eb-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="105eb-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="105eb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
