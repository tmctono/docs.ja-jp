---
title: シリアル化 (C#)
ms.date: 01/02/2020
ms.openlocfilehash: 1d2bda9022b7e43744dd8a0286eff88914cf65a3
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635731"
---
# <a name="serialization-c"></a><span data-ttu-id="a93a6-102">シリアル化 (C#)</span><span class="sxs-lookup"><span data-stu-id="a93a6-102">Serialization (C#)</span></span>

<span data-ttu-id="a93a6-103">シリアル化は、オブジェクトを格納するか、メモリ、データベース、またはファイルに転送するためにバイト ストリームに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="a93a6-103">Serialization is the process of converting an object into a stream of bytes to store the object or transmit it to memory, a database, or a file.</span></span> <span data-ttu-id="a93a6-104">その主な目的は、必要なときに再作成できるように、オブジェクトの状態を保存しておくことです。</span><span class="sxs-lookup"><span data-stu-id="a93a6-104">Its main purpose is to save the state of an object in order to be able to recreate it when needed.</span></span> <span data-ttu-id="a93a6-105">逆のプロセスは、逆シリアル化と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-105">The reverse process is called deserialization.</span></span>

## <a name="how-serialization-works"></a><span data-ttu-id="a93a6-106">シリアル化のしくみ</span><span class="sxs-lookup"><span data-stu-id="a93a6-106">How serialization works</span></span>

<span data-ttu-id="a93a6-107">この図は、シリアル化の全体的なプロセスを示しています:</span><span class="sxs-lookup"><span data-stu-id="a93a6-107">This illustration shows the overall process of serialization:</span></span>

![シリアル化グラフィック](./media/index/serialization-process.gif)

<span data-ttu-id="a93a6-109">オブジェクトが、データを格納するストリームにシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-109">The object is serialized to a stream that carries the data.</span></span> <span data-ttu-id="a93a6-110">ストリームには、バージョン、カルチャ、アセンブリ名など、オブジェクトの種類に関する情報が含まれている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a93a6-110">The stream may also have information about the object's type, such as its version, culture, and assembly name.</span></span> <span data-ttu-id="a93a6-111">そのストリームから、オブジェクトをデータベース、ファイル、またはメモリに格納できます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-111">From that stream, the object can be stored in a database, a file, or memory.</span></span>

### <a name="uses-for-serialization"></a><span data-ttu-id="a93a6-112">シリアル化の使用方法</span><span class="sxs-lookup"><span data-stu-id="a93a6-112">Uses for serialization</span></span>

<span data-ttu-id="a93a6-113">開発者は、シリアル化を使用して、オブジェクトの状態を保存し、必要に応じて、オブジェクトのストレージとデータ交換を指定することで、オブジェクトを再作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-113">Serialization allows the developer to save the state of an object and re-create it as needed, providing storage of objects as well as data exchange.</span></span> <span data-ttu-id="a93a6-114">開発者は、シリアル化を使用して次のようなアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-114">Through serialization, a developer can perform actions such as:</span></span>

* <span data-ttu-id="a93a6-115">Web サービスを使用してオブジェクトをリモート アプリケーションに送信する</span><span class="sxs-lookup"><span data-stu-id="a93a6-115">Sending the object to a remote application by using a web service</span></span>
* <span data-ttu-id="a93a6-116">オブジェクトをあるドメインから別のドメインに渡す</span><span class="sxs-lookup"><span data-stu-id="a93a6-116">Passing an object from one domain to another</span></span>
* <span data-ttu-id="a93a6-117">ファイアウォールを介してオブジェクトを JSON または XML 文字列として渡す</span><span class="sxs-lookup"><span data-stu-id="a93a6-117">Passing an object through a firewall as a JSON or XML string</span></span>
* <span data-ttu-id="a93a6-118">アプリケーション間でセキュリティまたはユーザー固有の情報を保持する</span><span class="sxs-lookup"><span data-stu-id="a93a6-118">Maintaining security or user-specific information across applications</span></span>

## <a name="json-serialization"></a><span data-ttu-id="a93a6-119">JSON シリアル化</span><span class="sxs-lookup"><span data-stu-id="a93a6-119">JSON serialization</span></span>

<span data-ttu-id="a93a6-120"><xref:System.Text.Json> 名前空間には、JavaScript Object Notation (JSON) シリアル化および逆シリアル化のためのクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a93a6-120">The <xref:System.Text.Json> namespace contains classes for JavaScript Object Notation (JSON) serialization and deserialization.</span></span> <span data-ttu-id="a93a6-121">JSON は、Web 経由でデータを共有するために一般的に使用されるオープン標準です。</span><span class="sxs-lookup"><span data-stu-id="a93a6-121">JSON is an open standard that is commonly used for sharing data across the web.</span></span>

<span data-ttu-id="a93a6-122">JSON シリアル化では、オブジェクトのパブリック プロパティが、[RFC 8259 JSON 仕様](https://tools.ietf.org/html/rfc8259)に準拠した文字列、バイト配列、またはストリームにシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-122">JSON serialization serializes the public properties of an object into a string, byte array, or stream that conforms to [the RFC 8259 JSON specification](https://tools.ietf.org/html/rfc8259).</span></span> <span data-ttu-id="a93a6-123"><xref:System.Text.Json.JsonSerializer> でクラスのインスタンスをシリアル化または逆シリアル化する方法を制御するには、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="a93a6-123">To control the way <xref:System.Text.Json.JsonSerializer> serializes or deserializes an instance of the class:</span></span>

* <span data-ttu-id="a93a6-124"><xref:System.Text.Json.JsonSerializerOptions> オブジェクトを使用する</span><span class="sxs-lookup"><span data-stu-id="a93a6-124">Use a <xref:System.Text.Json.JsonSerializerOptions> object</span></span>
* <span data-ttu-id="a93a6-125"><xref:System.Text.Json.Serialization> 名前空間からクラスまたはプロパティに属性を適用する</span><span class="sxs-lookup"><span data-stu-id="a93a6-125">Apply attributes from the <xref:System.Text.Json.Serialization> namespace to classes or properties</span></span>
* [<span data-ttu-id="a93a6-126">カスタム コンバーターを実装する</span><span class="sxs-lookup"><span data-stu-id="a93a6-126">Implement custom converters</span></span>](../../../../standard/serialization/system-text-json-converters-how-to.md)

## <a name="binary-and-xml-serialization"></a><span data-ttu-id="a93a6-127">バイナリ シリアル化と XML シリアル化</span><span class="sxs-lookup"><span data-stu-id="a93a6-127">Binary and XML serialization</span></span>

<span data-ttu-id="a93a6-128"><xref:System.Runtime.Serialization> 名前空間には、バイナリおよび XML シリアル化および逆シリアル化のためのクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a93a6-128">The <xref:System.Runtime.Serialization> namespace contains classes for binary and XML serialization and deserialization.</span></span>

<span data-ttu-id="a93a6-129">バイナリ シリアル化では、バイナリ エンコードを使用して、ストレージやソケット ベースのネットワーク ストリームなどのためのコンパクトなシリアル化を生成します。</span><span class="sxs-lookup"><span data-stu-id="a93a6-129">Binary serialization uses binary encoding to produce compact serialization for uses such as storage or socket-based network streams.</span></span> <span data-ttu-id="a93a6-130">バイナリ シリアル化では、読み取り専用メンバーも含め、すべてのメンバーがシリアル化され、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="a93a6-130">In binary serialization, all members, even members that are read-only, are serialized, and performance is enhanced.</span></span> 

<span data-ttu-id="a93a6-131">XML シリアル化では、オブジェクトのパブリック フィールドやパブリック プロパティ、またはメソッドのパラメーターや戻り値を、特定の XML スキーマ定義言語 (XSD) ドキュメントに準拠する XML ストリームにシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="a93a6-131">XML serialization serializes the public fields and properties of an object, or the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="a93a6-132">XML シリアル化では、XML に変換されるパブリック プロパティとパブリック フィールドによって厳密に型指定されたクラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-132">XML serialization results in strongly typed classes with public properties and fields that are converted to XML.</span></span> <span data-ttu-id="a93a6-133"><xref:System.Xml.Serialization> には、XML のシリアル化および逆シリアル化のためのクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a93a6-133"><xref:System.Xml.Serialization> contains classes for serializing and deserializing XML.</span></span> <span data-ttu-id="a93a6-134">属性をクラスおよびクラス メンバーに適用すると、<xref:System.Xml.Serialization.XmlSerializer> がそのクラスのインスタンスをシリアル化または逆シリアル化する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-134">You apply attributes to classes and class members to control the way the <xref:System.Xml.Serialization.XmlSerializer> serializes or deserializes an instance of the class.</span></span>

### <a name="making-an-object-serializable"></a><span data-ttu-id="a93a6-135">オブジェクトをシリアル化可能にする</span><span class="sxs-lookup"><span data-stu-id="a93a6-135">Making an object serializable</span></span>

<span data-ttu-id="a93a6-136">バイナリまたは XML シリアル化には、次が必要です。</span><span class="sxs-lookup"><span data-stu-id="a93a6-136">For binary or XML serialization, you need:</span></span>

* <span data-ttu-id="a93a6-137">シリアル化対象のオブジェクト</span><span class="sxs-lookup"><span data-stu-id="a93a6-137">The object to be serialized</span></span>
* <span data-ttu-id="a93a6-138">シリアル化されたオブジェクトを格納するストリーム</span><span class="sxs-lookup"><span data-stu-id="a93a6-138">A stream to contain the serialized object</span></span>
* <span data-ttu-id="a93a6-139"><xref:System.Runtime.Serialization.Formatter?displayProperty=fullName> のインスタンス</span><span class="sxs-lookup"><span data-stu-id="a93a6-139">A <xref:System.Runtime.Serialization.Formatter?displayProperty=fullName> instance</span></span>

<span data-ttu-id="a93a6-140">この型のインスタンスをシリアル化できることを示すには、<xref:System.SerializableAttribute> 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="a93a6-140">Apply the <xref:System.SerializableAttribute> attribute to a type to indicate that instances of the type can be serialized.</span></span> <span data-ttu-id="a93a6-141">型に <xref:System.SerializableAttribute> 属性が適用されていない状態でシリアル化しようとすると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-141">An  exception is thrown if you attempt to serialize but the type doesn't have the <xref:System.SerializableAttribute> attribute.</span></span>

<span data-ttu-id="a93a6-142">フィールドがシリアル化されないようにするには、<xref:System.NonSerializedAttribute> 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="a93a6-142">To prevent a field from being serialized, apply the <xref:System.NonSerializedAttribute> attribute.</span></span> <span data-ttu-id="a93a6-143">シリアル化できる型のフィールドに、特定の環境に固有のポインター、ハンドル、その他のデータ構造が含まれているときに、そのフィールドを別の環境で意味があるように再構成できない場合は、シリアル化不可にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-143">If a field of a serializable type contains a pointer, a handle, or some other data structure that is specific to a particular environment, and the field cannot be meaningfully reconstituted in a different environment, then you may want to make it nonserializable.</span></span>

<span data-ttu-id="a93a6-144">シリアル化されたクラスに、<xref:System.SerializableAttribute> とマークされている他のクラスのオブジェクトへの参照が含まれている場合は、これらのオブジェクトもシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-144">If a serialized class contains references to objects of other classes that are marked <xref:System.SerializableAttribute>, those objects will also be serialized.</span></span>

### <a name="basic-and-custom-serialization"></a><span data-ttu-id="a93a6-145">基本的なシリアル化とカスタムのシリアル化</span><span class="sxs-lookup"><span data-stu-id="a93a6-145">Basic and custom serialization</span></span>

<span data-ttu-id="a93a6-146">バイナリおよび XML シリアル化は、2 つの方法で実行できます (基本およびカスタム)。</span><span class="sxs-lookup"><span data-stu-id="a93a6-146">Binary and XML serialization can be performed in two ways, basic and custom.</span></span>

<span data-ttu-id="a93a6-147">基本的なシリアル化では、.NET Framework を使用して、オブジェクトが自動的にシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-147">Basic serialization uses the .NET Framework to automatically serialize the object.</span></span> <span data-ttu-id="a93a6-148">唯一の要件は、クラスに <xref:System.SerializableAttribute> 属性が適用されていることです。</span><span class="sxs-lookup"><span data-stu-id="a93a6-148">The only requirement is that the class has the <xref:System.SerializableAttribute> attribute applied.</span></span> <span data-ttu-id="a93a6-149"><xref:System.NonSerializedAttribute> を使用して、特定のフィールドがシリアル化されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-149">The <xref:System.NonSerializedAttribute> can be used to keep specific fields from being serialized.</span></span>

<span data-ttu-id="a93a6-150">基本的なシリアル化を使用する場合、オブジェクトのバージョン管理によって問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a93a6-150">When you use basic serialization, the versioning of objects may create problems.</span></span> <span data-ttu-id="a93a6-151">バージョン管理の問題が重要な場合は、カスタムのシリアル化を使用します。</span><span class="sxs-lookup"><span data-stu-id="a93a6-151">You would use custom serialization when versioning issues are important.</span></span> <span data-ttu-id="a93a6-152">基本的なシリアル化は、シリアル化を実行する最も簡単な方法ですが、プロセスを細かく制御することはできません。</span><span class="sxs-lookup"><span data-stu-id="a93a6-152">Basic serialization is the easiest way to perform serialization, but it does not provide much control over the process.</span></span>

<span data-ttu-id="a93a6-153">カスタムのシリアル化では、シリアル化するオブジェクトとシリアル化の方法を正確を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-153">In custom serialization, you can specify exactly which objects will be serialized and how it will be done.</span></span> <span data-ttu-id="a93a6-154">クラスを <xref:System.SerializableAttribute> でマークし、<xref:System.Runtime.Serialization.ISerializable> インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a93a6-154">The class must be marked <xref:System.SerializableAttribute> and implement the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span> <span data-ttu-id="a93a6-155">カスタムの方法でオブジェクトを逆シリアル化する場合は、カスタム コンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a93a6-155">If you want your object to be deserialized in a custom manner as well, use a custom constructor.</span></span>

## <a name="designer-serialization"></a><span data-ttu-id="a93a6-156">デザイナーのシリアル化</span><span class="sxs-lookup"><span data-stu-id="a93a6-156">Designer serialization</span></span>

<span data-ttu-id="a93a6-157">デザイナーのシリアル化はシリアル化の特殊な形式であり、開発ツールに関連付けられているオブジェクトの永続性の種類を含みます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-157">Designer serialization is a special form of serialization that involves the kind of object persistence associated with development tools.</span></span> <span data-ttu-id="a93a6-158">デザイナーのシリアル化は、後でオブジェクト グラフを復元できるように、オブジェクト グラフをソース ファイルに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="a93a6-158">Designer serialization is the process of converting an object graph into a source file that can later be used to recover the object graph.</span></span> <span data-ttu-id="a93a6-159">ソース ファイルには、コードとマークアップを含めることができますが、SQL テーブル情報を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="a93a6-159">A source file can contain code, markup, or even SQL table information.</span></span>

## <span data-ttu-id="a93a6-160"><a name="BKMK_RelatedTopics">関連トピックと例</a></span><span class="sxs-lookup"><span data-stu-id="a93a6-160"><a name="BKMK_RelatedTopics"></a> Related Topics and Examples</span></span>  

<span data-ttu-id="a93a6-161">[System.Text.Json の概要](../../../../standard/serialization/system-text-json-overview.md)。`System.Text.Json` ライブラリを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a93a6-161">[System.Text.Json overview](../../../../standard/serialization/system-text-json-overview.md) Shows how to get the `System.Text.Json` library.</span></span>

<span data-ttu-id="a93a6-162">[.NET で JSON をシリアル化および逆シリアル化する方法](../../../../standard/serialization/system-text-json-how-to.md)。</span><span class="sxs-lookup"><span data-stu-id="a93a6-162">[How to serialize and deserialize JSON in .NET](../../../../standard/serialization/system-text-json-how-to.md).</span></span> <span data-ttu-id="a93a6-163"><xref:System.Text.Json.JsonSerializer> クラスを使用して JSON との間でオブジェクト データの読み取りと書き込みを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a93a6-163">Shows how to read and write object data to and from JSON using the <xref:System.Text.Json.JsonSerializer> class.</span></span>

[<span data-ttu-id="a93a6-164">チュートリアル: オブジェクトの永続化 (Visual Studio (C#))</span><span class="sxs-lookup"><span data-stu-id="a93a6-164">Walkthrough: Persisting an Object in Visual Studio (C#)</span></span>](walkthrough-persisting-an-object-in-visual-studio.md)  
<span data-ttu-id="a93a6-165">シリアル化によってインスタンス間でオブジェクトのデータを永続化して値を保存しておき、次にそのオブジェクトをインスタンス化するときにその値を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a93a6-165">Demonstrates how serialization can be used to persist an object's data between instances, allowing you to store values and retrieve them the next time the object is instantiated.</span></span>

[<span data-ttu-id="a93a6-166">XML ファイルからオブジェクト データを読み取る方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="a93a6-166">How to read object data from an XML file (C#)</span></span>](how-to-read-object-data-from-an-xml-file.md)  
<span data-ttu-id="a93a6-167"><xref:System.Xml.Serialization.XmlSerializer> クラスを使用して、XML ファイルに以前に書き込まれたオブジェクト データを読み込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a93a6-167">Shows how to read object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>

[<span data-ttu-id="a93a6-168">XML ファイルにオブジェクト データを書き込む方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="a93a6-168">How to write object data to an XML file (C#)</span></span>](how-to-write-object-data-to-an-xml-file.md)  
<span data-ttu-id="a93a6-169"><xref:System.Xml.Serialization.XmlSerializer> クラスを使用して、クラスから XML ファイルにオブジェクトを書き込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a93a6-169">Shows how to write the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>
