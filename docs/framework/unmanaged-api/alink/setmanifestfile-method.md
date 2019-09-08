---
title: SetManifestFile メソッド
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b293c30060107d18c6b609efc82c4128a73cc1c7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787207"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="5a05e-102">SetManifestFile メソッド</span><span class="sxs-lookup"><span data-stu-id="5a05e-102">SetManifestFile Method</span></span>
<span data-ttu-id="5a05e-103">リンカーがアセンブリを作成するときに使用するマニフェストファイルを指定またはリセットできます。</span><span class="sxs-lookup"><span data-stu-id="5a05e-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a05e-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a05e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a05e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a05e-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="5a05e-106">コンテンツが Win32 リソース blob に格納されるマニフェストファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="5a05e-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a05e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="5a05e-107">Return Value</span></span>  
 <span data-ttu-id="5a05e-108">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="5a05e-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a05e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="5a05e-109">Remarks</span></span>  
 <span data-ttu-id="5a05e-110">Win32ResBlob を要求する前に、これを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5a05e-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="5a05e-111">`pszFile`パラメーターの値は、コンテンツが読み取られ、ID が RT_MANIFEST の Win32 リソースに格納されるマニフェストファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="5a05e-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="5a05e-112">NULL のパラメーターを使用して呼び出されると、以前に読み取られたマニフェストはクリアされます。</span><span class="sxs-lookup"><span data-stu-id="5a05e-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="5a05e-113">これにより、1つのリンカーの状態を初期化時間にリセットできます。</span><span class="sxs-lookup"><span data-stu-id="5a05e-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a05e-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="5a05e-114">Requirements</span></span>  
 <span data-ttu-id="5a05e-115">ALink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="5a05e-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a05e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a05e-116">See also</span></span>

- [<span data-ttu-id="5a05e-117">IALink3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a05e-117">IALink3 Interface</span></span>](ialink3-interface.md)
- [<span data-ttu-id="5a05e-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="5a05e-118">ALink API</span></span>](index.md)
- [<span data-ttu-id="5a05e-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a05e-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5a05e-120">Al.exe (アセンブリ リンカー)</span><span class="sxs-lookup"><span data-stu-id="5a05e-120">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
