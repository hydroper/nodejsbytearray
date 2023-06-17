# NodeJS byte array

Growable byte array for Node.js.

## Installation

```sh
npm i com.hydroper.util.nodejsbytearray
```

## API

```typescript
export type Endian = 'littleEndian' | 'bigEndian';

export declare default class ByteArray {
    constructor();

    static from(argument: ByteArray | Buffer): ByteArray;
    static withCapacity(initialCapacity: number): ByteArray;
    static withZeroes(length: number): ByteArray;

    toNodejsBuffer(): Buffer;
    *[Symbol.iterator](): Generator<number>;

    endian: Endian;
    position: number;
    readonly length: number;
    readonly bytesAvailable: number;
    readonly hasBytesAvailable: boolean;

    /**
     * Clears the array. `keepCapacity` is false by default.
     */
    clear(keepCapacity?: boolean);

    at(position: number): number;
    set(position: number, value: number);

    /**
     * Reads unsigned byte.
     */
    readByte(): number;

    /**
     * Writes unsigned byte.
     */
    writeByte(value: number);

    readSignedByte(): number;
    writeSignedByte(value: number);

    readShort(): number;
    writeShort(value: number);

    readUnsignedShort(): number;
    writeUnsignedShort(value: number);

    readInt(): number;
    writeInt(value: number);

    readUnsignedInt(): number;
    writeUnsignedInt(value: number);

    readLong(): bigint;
    writeLong(value: bigint);

    readUnsignedLong(): bigint;
    writeUnsignedLong(value: bigint);

    readFloat(): number;
    writeFloat(value: number);

    readDouble(): number;
    writeDouble(value: number);

    readUTF8(length: number): string;
    writeUTF8(value: string);

    readBytes(length: number): ByteArray;
    writeBytes(value: ByteArray);
}
```