---
title: ICorDebugSymbolProvider::GetMethodParameterSymbols メソッド
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
ms.openlocfilehash: 051002b547aaa9745ae4efb516211123089c3128
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379597"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a><span data-ttu-id="cf7f0-102">ICorDebugSymbolProvider::GetMethodParameterSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="cf7f0-102">ICorDebugSymbolProvider::GetMethodParameterSymbols Method</span></span>
<span data-ttu-id="cf7f0-103">メソッドの指定の相対仮想アドレス (RVA: relative virtual address ) で、そのメソッドのパラメーター シンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="cf7f0-103">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf7f0-104">構文</span><span class="sxs-lookup"><span data-stu-id="cf7f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf7f0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf7f0-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="cf7f0-106">[in] メソッドのネイティブ相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="cf7f0-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="cf7f0-107">[in] ローカル シンボルの要求数。</span><span class="sxs-lookup"><span data-stu-id="cf7f0-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="cf7f0-108">[out] メソッドによって取得されたシンボル数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cf7f0-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="cf7f0-109">入出力メソッドのローカルシンボルを格納している[ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cf7f0-109">[out] A pointer to an [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf7f0-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf7f0-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cf7f0-111">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf7f0-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf7f0-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="cf7f0-112">Requirements</span></span>  
 <span data-ttu-id="cf7f0-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf7f0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf7f0-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf7f0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf7f0-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf7f0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf7f0-116">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf7f0-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf7f0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf7f0-117">See also</span></span>

- [<span data-ttu-id="cf7f0-118">GetMethodLocalSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="cf7f0-118">GetMethodLocalSymbols Method</span></span>](icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [<span data-ttu-id="cf7f0-119">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cf7f0-119">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="cf7f0-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="cf7f0-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
