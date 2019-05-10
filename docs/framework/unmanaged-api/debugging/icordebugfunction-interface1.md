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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 550b85474c1ccd7e125549e86df906439caf410e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621497"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="1e525-102">ICorDebugFunction インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e525-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="1e525-103">マネージド関数またはマネージド メソッドを表します。</span><span class="sxs-lookup"><span data-stu-id="1e525-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1e525-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1e525-104">Methods</span></span>  
  
|<span data-ttu-id="1e525-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1e525-105">Method</span></span>|<span data-ttu-id="1e525-106">説明</span><span class="sxs-lookup"><span data-stu-id="1e525-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1e525-107">CreateBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="1e525-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="1e525-108">この関数の先頭にブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1e525-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="1e525-109">GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="1e525-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="1e525-110">この関数のメンバーであるクラスを表す ICorDebugClass オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="1e525-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="1e525-111">GetCurrentVersionNumber メソッド</span><span class="sxs-lookup"><span data-stu-id="1e525-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="1e525-112">この関数に対して行われた最新の編集のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="1e525-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="1e525-113">GetILCode メソッド</span><span class="sxs-lookup"><span data-stu-id="1e525-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="1e525-114">この関数の Microsoft intermediate language (MSIL) コードを取得します。</span><span class="sxs-lookup"><span data-stu-id="1e525-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="1e525-115">GetLocalVarSigToken メソッド</span><span class="sxs-lookup"><span data-stu-id="1e525-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="1e525-116">これで表される関数のローカル変数シグネチャのメタデータ トークンを取得`ICorDebugFunction`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="1e525-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="1e525-117">GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="1e525-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="1e525-118">この関数が定義されているモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="1e525-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="1e525-119">GetNativeCode メソッド</span><span class="sxs-lookup"><span data-stu-id="1e525-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="1e525-120">この関数のネイティブ コードを取得します。</span><span class="sxs-lookup"><span data-stu-id="1e525-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="1e525-121">GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="1e525-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="1e525-122">この関数のメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="1e525-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e525-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="1e525-123">Remarks</span></span>  
 <span data-ttu-id="1e525-124">`ICorDebugFunction`インターフェイスがジェネリック型パラメーターを持つ関数を表していません。</span><span class="sxs-lookup"><span data-stu-id="1e525-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="1e525-125">たとえば、`ICorDebugFunction`はインスタンスを表します`Func<T>`なく`Func<string>`します。</span><span class="sxs-lookup"><span data-stu-id="1e525-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="1e525-126">呼び出す[icordebugilframe 2::enumeratetypeparameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)ジェネリック型パラメーターを取得します。</span><span class="sxs-lookup"><span data-stu-id="1e525-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="1e525-127">メソッドのメタデータのトークンの間のリレーションシップ`mdMethodDef`、およびメソッドの`ICorDebugFunction`オブジェクトは、関数の編集と続行を許可するかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1e525-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="1e525-128">間で一対一のリレーションシップが存在する場合は、関数、エディット コンティニュは許可されていません、`ICorDebugFunction`オブジェクトと`mdMethodDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="1e525-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="1e525-129">つまり、関数には 1 つ`ICorDebugFunction`オブジェクトと 1 つ`mdMethodDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="1e525-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="1e525-130">間で多対一のリレーションシップが存在する場合は、関数では、エディット コンティニュは許可して、`ICorDebugFunction`オブジェクトと`mdMethodDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="1e525-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="1e525-131">つまり、関数は多くのインスタンスのことは`ICorDebugFunction`、関数のバージョンごとに 1 つが、1 つだけ`mdMethodDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="1e525-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e525-132">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1e525-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e525-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="1e525-133">Requirements</span></span>  
 <span data-ttu-id="1e525-134">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e525-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e525-135">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e525-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e525-136">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e525-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e525-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e525-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e525-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e525-138">See also</span></span>

- [<span data-ttu-id="1e525-139">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e525-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
