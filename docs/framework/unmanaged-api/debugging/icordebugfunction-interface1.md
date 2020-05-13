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
ms.openlocfilehash: 6b7b6969c1f207decbf47217e98b7fee3aa9ce54
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213243"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="ab2f4-102">ICorDebugFunction インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ab2f4-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="ab2f4-103">マネージド関数またはマネージド メソッドを表します。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ab2f4-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="ab2f4-104">Methods</span></span>  
  
|<span data-ttu-id="ab2f4-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ab2f4-105">Method</span></span>|<span data-ttu-id="ab2f4-106">説明</span><span class="sxs-lookup"><span data-stu-id="ab2f4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ab2f4-107">CreateBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="ab2f4-107">CreateBreakpoint Method</span></span>](icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="ab2f4-108">この関数の先頭にブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="ab2f4-109">GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="ab2f4-109">GetClass Method</span></span>](icordebugfunction-getclass-method.md)|<span data-ttu-id="ab2f4-110">この関数がメンバーとなっているクラスを表す、のオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="ab2f4-111">GetCurrentVersionNumber メソッド</span><span class="sxs-lookup"><span data-stu-id="ab2f4-111">GetCurrentVersionNumber Method</span></span>](icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="ab2f4-112">この関数に対して行われた最新の編集のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="ab2f4-113">GetILCode メソッド</span><span class="sxs-lookup"><span data-stu-id="ab2f4-113">GetILCode Method</span></span>](icordebugfunction-getilcode-method.md)|<span data-ttu-id="ab2f4-114">この関数の MSIL (Microsoft 中間言語) コードを取得します。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="ab2f4-115">GetLocalVarSigToken メソッド</span><span class="sxs-lookup"><span data-stu-id="ab2f4-115">GetLocalVarSigToken Method</span></span>](icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="ab2f4-116">このインスタンスによって表される関数のローカル変数シグネチャのメタデータトークンを取得し `ICorDebugFunction` ます。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="ab2f4-117">GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="ab2f4-117">GetModule Method</span></span>](icordebugfunction-getmodule-method.md)|<span data-ttu-id="ab2f4-118">この関数が定義されているモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="ab2f4-119">GetNativeCode メソッド</span><span class="sxs-lookup"><span data-stu-id="ab2f4-119">GetNativeCode Method</span></span>](icordebugfunction-getnativecode-method.md)|<span data-ttu-id="ab2f4-120">この関数のネイティブコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="ab2f4-121">GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="ab2f4-121">GetToken Method</span></span>](icordebugfunction-gettoken-method.md)|<span data-ttu-id="ab2f4-122">この関数のメタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab2f4-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="ab2f4-123">Remarks</span></span>  
 <span data-ttu-id="ab2f4-124">インターフェイスは、 `ICorDebugFunction` ジェネリック型パラメーターを持つ関数を表していません。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="ab2f4-125">たとえば、インスタンスはを `ICorDebugFunction` 表しますが、では `Func<T>` ありません `Func<string>` 。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="ab2f4-126">[ICorDebugILFrame2:: EnumerateTypeParameters](icordebugilframe2-enumeratetypeparameters-method.md)を呼び出して、ジェネリック型パラメーターを取得します。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="ab2f4-127">メソッドのメタデータトークン、 `mdMethodDef` 、およびメソッドのオブジェクト間のリレーションシップ `ICorDebugFunction` は、関数でエディットコンティニュが許可されているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="ab2f4-128">関数でエディットコンティニュを使用できない場合は、オブジェクトとトークンの間に一対一のリレーションシップが存在し `ICorDebugFunction` `mdMethodDef` ます。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="ab2f4-129">つまり、関数は、1つの `ICorDebugFunction` オブジェクトと1つのトークンを持ち `mdMethodDef` ます。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="ab2f4-130">関数でエディットコンティニュが許可されている場合は、オブジェクトとトークンの間に多対一のリレーションシップが存在し `ICorDebugFunction` `mdMethodDef` ます。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="ab2f4-131">つまり、関数は、 `ICorDebugFunction` 関数の各バージョンに1つずつ、1つのトークンのみを含むのインスタンスを多数持つことができ `mdMethodDef` ます。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ab2f4-132">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab2f4-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="ab2f4-133">Requirements</span></span>  
 <span data-ttu-id="ab2f4-134">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab2f4-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab2f4-135">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab2f4-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab2f4-136">**ライブラリ:** CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="ab2f4-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab2f4-137">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab2f4-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab2f4-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab2f4-138">See also</span></span>

- [<span data-ttu-id="ab2f4-139">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ab2f4-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
