---
title: シンボル ストア診断インターフェイス
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
ms.openlocfilehash: bdb691570a9a2bf7bd2bb21af500b06c10b0bc53
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448527"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="9356d-102">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="9356d-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span><span class="sxs-lookup"><span data-stu-id="9356d-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9356d-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9356d-104">In This Section</span></span>  
 [<span data-ttu-id="9356d-105">IBindingDisplay インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="9356d-106">Provides methods that display current binding information about the running application.</span><span class="sxs-lookup"><span data-stu-id="9356d-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="9356d-107">IDebugAutoAttach インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="9356d-108">Defines the interface for a server-invoked debugger auto attach.</span><span class="sxs-lookup"><span data-stu-id="9356d-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="9356d-109">INotifyConnection2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="9356d-110">Declares methods for registering and unregistering a connection notification source.</span><span class="sxs-lookup"><span data-stu-id="9356d-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="9356d-111">INotifySink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="9356d-112">Declares methods for sink notification.</span><span class="sxs-lookup"><span data-stu-id="9356d-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="9356d-113">INotifySource2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="9356d-114">Declares a method for setting notification filters.</span><span class="sxs-lookup"><span data-stu-id="9356d-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="9356d-115">ISymENCUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="9356d-116">Provides information for the Edit and Continue feature.</span><span class="sxs-lookup"><span data-stu-id="9356d-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="9356d-117">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="9356d-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9356d-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="9356d-119">ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="9356d-120">Allows definition of optional async method information per method symbol.</span><span class="sxs-lookup"><span data-stu-id="9356d-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="9356d-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="9356d-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="9356d-122">ISymUnmanagedBinder インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="9356d-123">Represents a symbol binder for unmanaged code.</span><span class="sxs-lookup"><span data-stu-id="9356d-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="9356d-124">ISymUnmanagedBinder2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="9356d-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span><span class="sxs-lookup"><span data-stu-id="9356d-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="9356d-126">ISymUnmanagedBinder3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="9356d-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span><span class="sxs-lookup"><span data-stu-id="9356d-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="9356d-128">ISymUnmanagedConstant インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="9356d-129">Provides access to unmanaged constants.</span><span class="sxs-lookup"><span data-stu-id="9356d-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="9356d-130">ISymUnmanagedDispose インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="9356d-131">Disposes of unmanaged resources.</span><span class="sxs-lookup"><span data-stu-id="9356d-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="9356d-132">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="9356d-133">シンボル ストアによって参照されるドキュメントを表します。</span><span class="sxs-lookup"><span data-stu-id="9356d-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="9356d-134">ISymUnmanagedDocumentWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="9356d-135">シンボル ストアで参照されるドキュメントに書き込むためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="9356d-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="9356d-136">ISymUnmanagedENCUpdate インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="9356d-137">Provides methods for the Edit and Continue feature.</span><span class="sxs-lookup"><span data-stu-id="9356d-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="9356d-138">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="9356d-139">Represents a method within the symbol store.</span><span class="sxs-lookup"><span data-stu-id="9356d-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="9356d-140">ISymUnmanagedNamespace インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="9356d-141">Represents a namespace.</span><span class="sxs-lookup"><span data-stu-id="9356d-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="9356d-142">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="9356d-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span><span class="sxs-lookup"><span data-stu-id="9356d-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="9356d-144">ISymUnmanagedReader2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="9356d-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span><span class="sxs-lookup"><span data-stu-id="9356d-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="9356d-146">ISymUnmanagedReaderSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="9356d-147">Provides methods that get symbol search information.</span><span class="sxs-lookup"><span data-stu-id="9356d-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="9356d-148">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="9356d-149">Represents a lexical scope within a method.</span><span class="sxs-lookup"><span data-stu-id="9356d-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="9356d-150">ISymUnmanagedScope2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="9356d-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span><span class="sxs-lookup"><span data-stu-id="9356d-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="9356d-152">ISymUnmanagedSourceServerModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="9356d-153">Provides source server data for a module.</span><span class="sxs-lookup"><span data-stu-id="9356d-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="9356d-154">ISymUnmanagedSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="9356d-155">Provides methods that get information about the search path.</span><span class="sxs-lookup"><span data-stu-id="9356d-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="9356d-156">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="9356d-157">Represents a variable, such as a parameter, a local variable, or a field.</span><span class="sxs-lookup"><span data-stu-id="9356d-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="9356d-158">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="9356d-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span><span class="sxs-lookup"><span data-stu-id="9356d-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="9356d-160">ISymUnmanagedWriter2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="9356d-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span><span class="sxs-lookup"><span data-stu-id="9356d-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="9356d-162">Extends the `ISymUnmanagedWriter` interface.</span><span class="sxs-lookup"><span data-stu-id="9356d-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="9356d-163">ISymUnmanagedWriter3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="9356d-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span><span class="sxs-lookup"><span data-stu-id="9356d-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="9356d-165">Extends the `ISymUnmanagedWriter` interface.</span><span class="sxs-lookup"><span data-stu-id="9356d-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="9356d-166">ISymUnmanagedWriter4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="9356d-167">ISymUnmanagedWriter4 interface.</span><span class="sxs-lookup"><span data-stu-id="9356d-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="9356d-168">ISymUnmanagedWriter5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9356d-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="9356d-169">ISymUnmanagedWriter5 interface.</span><span class="sxs-lookup"><span data-stu-id="9356d-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9356d-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="9356d-170">Related Sections</span></span>  
 [<span data-ttu-id="9356d-171">シンボル ストア診断列挙型</span><span class="sxs-lookup"><span data-stu-id="9356d-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="9356d-172">シンボル ストア診断構造体</span><span class="sxs-lookup"><span data-stu-id="9356d-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="9356d-173">デバッグ</span><span class="sxs-lookup"><span data-stu-id="9356d-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
