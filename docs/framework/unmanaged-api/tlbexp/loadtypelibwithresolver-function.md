---
title: LoadTypeLibWithResolver 関数
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b78789344050fd5e1cb0ee3492bf330fbf92bc88
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798937"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="d6a10-102">LoadTypeLibWithResolver 関数</span><span class="sxs-lookup"><span data-stu-id="d6a10-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="d6a10-103">タイプライブラリを読み込み、指定された[ITypeLibResolver インターフェイス](itypelibresolver-interface.md)を使用して、内部で参照されているタイプライブラリを解決します。</span><span class="sxs-lookup"><span data-stu-id="d6a10-103">Loads a type library and uses the supplied [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6a10-104">構文</span><span class="sxs-lookup"><span data-stu-id="d6a10-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6a10-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6a10-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="d6a10-106">からタイプライブラリのファイルパス。</span><span class="sxs-lookup"><span data-stu-id="d6a10-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="d6a10-107">からタイプライブラリの登録方法を制御する[Regkind 列挙](https://docs.microsoft.com/windows/win32/api/oleauto/ne-oleauto-regkind)フラグ。</span><span class="sxs-lookup"><span data-stu-id="d6a10-107">[in] A [REGKIND enumeration](https://docs.microsoft.com/windows/win32/api/oleauto/ne-oleauto-regkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="d6a10-108">指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d6a10-108">Its possible values are:</span></span>  
  
- <span data-ttu-id="d6a10-109">`REGKIND_DEFAULT`:既定の登録動作を使用します。</span><span class="sxs-lookup"><span data-stu-id="d6a10-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
- <span data-ttu-id="d6a10-110">`REGKIND_REGISTER`:このタイプライブラリを登録します。</span><span class="sxs-lookup"><span data-stu-id="d6a10-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
- <span data-ttu-id="d6a10-111">`REGKIND_NONE` :このタイプライブラリを登録しないでください。</span><span class="sxs-lookup"><span data-stu-id="d6a10-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="d6a10-112">から[ITypeLibResolver インターフェイス](itypelibresolver-interface.md)の実装へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d6a10-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="d6a10-113">入出力読み込まれているタイプライブラリへの参照。</span><span class="sxs-lookup"><span data-stu-id="d6a10-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6a10-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="d6a10-114">Return Value</span></span>  
 <span data-ttu-id="d6a10-115">次の表に示す HRESULT 値の1つ。</span><span class="sxs-lookup"><span data-stu-id="d6a10-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="d6a10-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="d6a10-116">Return value</span></span>|<span data-ttu-id="d6a10-117">説明</span><span class="sxs-lookup"><span data-stu-id="d6a10-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="d6a10-118">成功。</span><span class="sxs-lookup"><span data-stu-id="d6a10-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="d6a10-119">メモリ不足。</span><span class="sxs-lookup"><span data-stu-id="d6a10-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="d6a10-120">1つ以上のポインターが無効です。</span><span class="sxs-lookup"><span data-stu-id="d6a10-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="d6a10-121">1つ以上の引数が無効です。</span><span class="sxs-lookup"><span data-stu-id="d6a10-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="d6a10-122">関数はファイルに書き込めませんでした。</span><span class="sxs-lookup"><span data-stu-id="d6a10-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="d6a10-123">システム登録データベースを開けませんでした。</span><span class="sxs-lookup"><span data-stu-id="d6a10-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="d6a10-124">タイプライブラリを開けませんでした。</span><span class="sxs-lookup"><span data-stu-id="d6a10-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="d6a10-125">タイプライブラリまたは DLL を読み込めませんでした。</span><span class="sxs-lookup"><span data-stu-id="d6a10-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6a10-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="d6a10-126">Remarks</span></span>  
 <span data-ttu-id="d6a10-127">[Tlbexp.exe (タイプライブラリエクスポーター)](../../tools/tlbexp-exe-type-library-exporter.md)は、アセンブリからタイプ`LoadTypeLibWithResolver`ライブラリへの変換プロセス中に関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d6a10-127">The [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="d6a10-128">この関数は、レジストリへの最小限のアクセスで、指定されたタイプライブラリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d6a10-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="d6a10-129">次に、関数は、内部的に参照されるタイプライブラリのタイプライブラリを調べます。このタイプライブラリはそれぞれ、親タイプライブラリに読み込まれ、追加される必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6a10-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="d6a10-130">参照されるタイプライブラリを読み込む前に、その参照ファイルのパスを完全なファイルパスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6a10-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="d6a10-131">これは、 `pTlbResolver`パラメーターで渡される[ITypeLibResolver インターフェイス](itypelibresolver-interface.md)によって提供される[resolvetypelib メソッド](resolvetypelib-method.md)を使用して実現されます。</span><span class="sxs-lookup"><span data-stu-id="d6a10-131">This is accomplished through the [ResolveTypeLib method](resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="d6a10-132">参照されているタイプライブラリの完全なファイルパスがわかっ`LoadTypeLibWithResolver`ている場合、この関数は参照されているタイプライブラリを読み込んで親タイプライブラリに追加し、結合されたマスタータイプライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d6a10-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="d6a10-133">関数は、内部的に参照されるすべてのタイプライブラリを解決して読み込み、 `pptlib`パラメーター内のマスター解決済みタイプライブラリへの参照を返します。</span><span class="sxs-lookup"><span data-stu-id="d6a10-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="d6a10-134">この関数は、通常、 [tlbexp.exe (タイプライブラリエクスポーター)](../../tools/tlbexp-exe-type-library-exporter.md)によって呼び出されます。これは、 `pTlbResolver`パラメーターに独自の内部[ITypeLibResolver インターフェイス](itypelibresolver-interface.md)実装を提供します。 `LoadTypeLibWithResolver`</span><span class="sxs-lookup"><span data-stu-id="d6a10-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="d6a10-135">を直接呼び出す`LoadTypeLibWithResolver`場合は、独自の[ITypeLibResolver インターフェイス](itypelibresolver-interface.md)実装を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6a10-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6a10-136">必要条件</span><span class="sxs-lookup"><span data-stu-id="d6a10-136">Requirements</span></span>  
 <span data-ttu-id="d6a10-137">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6a10-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6a10-138">**ヘッダー:** Tlf .h</span><span class="sxs-lookup"><span data-stu-id="d6a10-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="d6a10-139">**ライブラリ**Tlf .lib</span><span class="sxs-lookup"><span data-stu-id="d6a10-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="d6a10-140">**.NET Framework のバージョン:** 3.5、3.0、2.0</span><span class="sxs-lookup"><span data-stu-id="d6a10-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6a10-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6a10-141">See also</span></span>

- [<span data-ttu-id="d6a10-142">Tlbexp ヘルパー関数</span><span class="sxs-lookup"><span data-stu-id="d6a10-142">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="d6a10-143">LoadTypeLibEx 関数</span><span class="sxs-lookup"><span data-stu-id="d6a10-143">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
