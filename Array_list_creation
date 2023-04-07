
public class Array_List<E> {
    private int size;

    private E[] elements;
    private static final int DEFAULT_CAPACITY = 10;

    public Array_List(int capacity) {
        capacity = (capacity < DEFAULT_CAPACITY) ? DEFAULT_CAPACITY : capacity;
        elements =  (E[])new Object[capacity];
    }

    public Array_List() {
        elements = (E[]) new Object[DEFAULT_CAPACITY];
        // this(DEFAULT_CAPACITY);
    }

    public int size() {
        return this.size;
    }

    public boolean isEmpty() {
        return size == 0;
    }

    public E get(int index) {
        if (index < 0 || index >= size)
            throw new IndexOutOfBoundsException("Error of index"); //抛出异常
        return elements[index];
    }

    public E set(int index, E element) {
        if (index < 0 || index >= size)
            throw new IndexOutOfBoundsException("Error of index"); //抛出异常
        E old = elements[index];
        elements[index] = element;
        return old;
    }

    public int indexOf(E element) {
        if(element == null){
            for(int i = 0; i < size; i++){
                if(elements[i] == null) return i;
            }
        }else{
            for (int i = 0; i < size; i++)
                if (elements[i].equals(element)) return i;
        }
        return ELEMENT_NOT_FOUND;
    }

    public boolean contains(E element) {
        return indexOf(element) != ELEMENT_NOT_FOUND;
    }

    public void clear() {
        for(int i = 0; i < size; i++){
            elements[i] = null;

        }
        size = 0;


    }

    public void add(E element) {
        add(size, element);
    }

    public void add(int index, E element) {
        size++;
        ensureCapacity(size + 1);
        for(int i = size ; i>= index; i--){
            elements[size] = elements[size - 1];
        }
        elements[index] = element;


    }
    private void ensureCapacity(int capacity){
        int oldCapacity = elements.length;
        if(oldCapacity >= capacity) return;

        oldCapacity = oldCapacity + (oldCapacity >> 1);
        E[] newArray =(E[]) new Object[oldCapacity];
        for (int i = 0; i < size; i++) {
            newArray[i] = elements[i];
        elements = newArray;
        }
    }
    @Override
    public String toString() {
            StringBuilder string = new StringBuilder();
            string.append("size= ").append(size).append(",[");
            for(int i = 0; i < size; i++){
                if(i != 0){
                    string.append(", ");
                }
                string.append(elements[i]);
            }
            string.append(",");
            return string.toString();
    }
    public E remove(int index) {
        E result = elements[index];
        for (int i = index + 1 ; i <= size - 1 ; i++) {
            elements[i - 1] = elements[index];
        }
        elements[--size] = null;
        return result;
    }
}
