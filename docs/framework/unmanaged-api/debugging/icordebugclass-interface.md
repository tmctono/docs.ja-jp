---
title: ICorDebugClass インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
ms.openlocfilehash: d7417e8dc193172c77d23fe3fa72c8298d802b5c
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894039"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="8e834-102">ICorDebugClass インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e834-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="8e834-103">基本型または複合型 (つまり、ユーザー定義) のいずれかの型を表します。</span><span class="sxs-lookup"><span data-stu-id="8e834-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="8e834-104">型がジェネリックの場合、`ICorDebugClass` はインスタンス化されないジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="8e834-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e834-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8e834-105">Methods</span></span>  
  
|<span data-ttu-id="8e834-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="8e834-106">Method</span></span>|<span data-ttu-id="8e834-107">説明</span><span class="sxs-lookup"><span data-stu-id="8e834-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e834-108">GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="8e834-108">GetModule Method</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="8e834-109">このクラスを定義するモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="8e834-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="8e834-110">GetStaticFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="8e834-110">GetStaticFieldValue Method</span></span>](icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="8e834-111">指定された静的フィールドの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="8e834-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="8e834-112">GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="8e834-112">GetToken Method</span></span>](icordebugclass-gettoken-method.md)|<span data-ttu-id="8e834-113">このクラス`TypeDef`のメタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="8e834-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e834-114">解説</span><span class="sxs-lookup"><span data-stu-id="8e834-114">Remarks</span></span>  
 <span data-ttu-id="8e834-115">インターフェイス`ICorDebugClass`は、インスタンスジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="8e834-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="8e834-116">は、インスタンス化されたジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="8e834-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="8e834-117">たとえば、 `Hashtable<K, V>`はで`ICorDebugClass` `Hashtable<Int32, String>`表されますが、はによっ`ICorDebugType`て表されます。</span><span class="sxs-lookup"><span data-stu-id="8e834-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="8e834-118">非ジェネリック型は、と`ICorDebugClass` `ICorDebugType`の両方で表されます。</span><span class="sxs-lookup"><span data-stu-id="8e834-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="8e834-119">後者のインターフェイスは、型のインスタンス化を処理するために .NET Framework バージョン2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8e834-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e834-120">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8e834-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e834-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="8e834-121">Requirements</span></span>  
 <span data-ttu-id="8e834-122">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e834-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e834-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e834-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e834-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e834-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e834-125">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e834-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e834-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e834-126">See also</span></span>

- [<span data-ttu-id="8e834-127">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e834-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
