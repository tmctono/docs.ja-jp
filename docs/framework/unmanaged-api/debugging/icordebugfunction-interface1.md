---
title: ICorDebugFunction インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
ms.openlocfilehash: eb2b1e218314be01898ce90c4378fb713f9bf6ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137848"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="39a4f-102">ICorDebugFunction インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39a4f-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="39a4f-103">マネージド関数またはマネージド メソッドを表します。</span><span class="sxs-lookup"><span data-stu-id="39a4f-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="39a4f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="39a4f-104">Methods</span></span>  
  
|<span data-ttu-id="39a4f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="39a4f-105">Method</span></span>|<span data-ttu-id="39a4f-106">説明</span><span class="sxs-lookup"><span data-stu-id="39a4f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="39a4f-107">CreateBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="39a4f-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="39a4f-108">この関数の先頭にブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="39a4f-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="39a4f-109">GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="39a4f-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="39a4f-110">この関数がメンバーとなっているクラスを表す、のオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="39a4f-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="39a4f-111">GetCurrentVersionNumber メソッド</span><span class="sxs-lookup"><span data-stu-id="39a4f-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="39a4f-112">この関数に対して行われた最新の編集のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="39a4f-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="39a4f-113">GetILCode メソッド</span><span class="sxs-lookup"><span data-stu-id="39a4f-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="39a4f-114">この関数の MSIL (Microsoft 中間言語) コードを取得します。</span><span class="sxs-lookup"><span data-stu-id="39a4f-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="39a4f-115">GetLocalVarSigToken メソッド</span><span class="sxs-lookup"><span data-stu-id="39a4f-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="39a4f-116">この `ICorDebugFunction` インスタンスによって表される関数のローカル変数シグネチャのメタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="39a4f-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="39a4f-117">GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="39a4f-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="39a4f-118">この関数が定義されているモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="39a4f-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="39a4f-119">GetNativeCode メソッド</span><span class="sxs-lookup"><span data-stu-id="39a4f-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="39a4f-120">この関数のネイティブコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="39a4f-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="39a4f-121">GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="39a4f-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="39a4f-122">この関数のメタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="39a4f-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39a4f-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="39a4f-123">Remarks</span></span>  
 <span data-ttu-id="39a4f-124">`ICorDebugFunction` インターフェイスは、ジェネリック型パラメーターを持つ関数を表していません。</span><span class="sxs-lookup"><span data-stu-id="39a4f-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="39a4f-125">たとえば、`ICorDebugFunction` インスタンスは `Func<T>` を表しますが `Func<string>`は表しません。</span><span class="sxs-lookup"><span data-stu-id="39a4f-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="39a4f-126">[ICorDebugILFrame2:: EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)を呼び出して、ジェネリック型パラメーターを取得します。</span><span class="sxs-lookup"><span data-stu-id="39a4f-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="39a4f-127">メソッドのメタデータトークン、`mdMethodDef`、およびメソッドの `ICorDebugFunction` オブジェクト間のリレーションシップは、関数でエディットコンティニュが許可されているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="39a4f-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="39a4f-128">関数でエディットコンティニュが許可されていない場合、`ICorDebugFunction` オブジェクトと `mdMethodDef` トークンの間には一対一のリレーションシップが存在します。</span><span class="sxs-lookup"><span data-stu-id="39a4f-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="39a4f-129">つまり、関数は、1つの `ICorDebugFunction` オブジェクトと1つの `mdMethodDef` トークンを持ちます。</span><span class="sxs-lookup"><span data-stu-id="39a4f-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="39a4f-130">関数でエディットコンティニュが許可されている場合、`ICorDebugFunction` オブジェクトと `mdMethodDef` トークンの間に多対一のリレーションシップが存在します。</span><span class="sxs-lookup"><span data-stu-id="39a4f-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="39a4f-131">つまり、関数は、関数の各バージョンに対して1つずつ `ICorDebugFunction`のインスタンスを多数持つことができますが、`mdMethodDef` トークンは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="39a4f-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="39a4f-132">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="39a4f-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39a4f-133">［要件］</span><span class="sxs-lookup"><span data-stu-id="39a4f-133">Requirements</span></span>  
 <span data-ttu-id="39a4f-134">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39a4f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39a4f-135">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39a4f-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39a4f-136">**ライブラリ:** CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="39a4f-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="39a4f-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39a4f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a4f-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="39a4f-138">See also</span></span>

- [<span data-ttu-id="39a4f-139">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39a4f-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
